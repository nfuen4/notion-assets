# Incident Post-Mortem & Troubleshooting Log: Notion MCP & Asset Pipeline

**Date:** 2026-10-24  
**Impacted Systems:** Notion MCP Server (`@notionhq/notion-mcp-server`), Google Antigravity Agent Sessions, ChatGPT/External LLM API Integrations  
**Integration Name:** Bossman Gravitas  
**Asset Repository:** [`nfuen4/notion-assets`](https://github.com/nfuen4/notion-assets)  

---

## 1. Executive Summary

During attempts to embed local infographic images and upload lengthy chapter study notes to Notion pages, sessions encountered repeated delays, `400 Validation Errors`, and confusion over JSON payloads. 

The core issues were resolved:
1. **Asset Pipeline Hardened**: Local image uploads now automatically route through the public `nfuen4/notion-assets` GitHub repository via `gh api` and deliver raw CDN URLs to Notion in **< 2 seconds**.
2. **Global Codification**: The asset protocol was permanently committed into `~/.gemini/config/AGENTS.md` and `~/.gemini/config/skills/notion-page-editor/SKILL.md`, preventing future sessions from attempting rejected `file://` transfers.
3. **Page Markdown Synchronization**: Shifted full-page text ingestion from manual JSON block chunking (30–60s) to Notion's native `API-update-page-markdown` (`replace_content`) endpoint (executed in **0.8s** for 32KB of formatted notes).

---

## 2. Detailed Root Cause Analysis (RCA)

### Issue A: Local Image Upload Failures (`400 Invalid image url`)
* **Symptom:** Passing local disk paths (e.g. `file:///Users/nevinfuentes/.../image.jpg`) to Notion's `API-patch-block-children` resulted in:
  ```json
  {"status": 400, "code": "validation_error", "message": "Content creation Failed. Fix the following: Invalid image url."}
  ```
* **Root Cause:** The official Notion REST API strictly forbids local file protocol URIs (`file://`) and base64 byte streams in block creation. It requires either:
  1. A live, publicly reachable HTTPS URL (`type: "external"`), or
  2. A pre-existing server-side `file_upload.id` from Notion's internal file service.
* **Why it Worked Historically:** In earlier sessions, an agent silently committed the images to `nfuen4/notion-assets` first, then passed `raw.githubusercontent.com/...` to Notion. Because that intermediary step was never codified as a global rule, fresh sessions lacked memory of the pattern and attempted direct local uploads.

### Issue B: The "Object Block" Misinterpretation
* **Symptom:** User observed repeated key-value pairs of `"object": "block"` and suspected an authorization lock, security blockage, or connection failure.
* **Root Cause:** Notion's API data model classifies every UI element (paragraphs, headers, images, dividers, toggles) as an individual `block`. The response key `"object": "block"` is Notion's schema descriptor, confirming the element was successfully recognized as a block—not that access was blocked.

### Issue C: UUID Formatting Rejections (`404 object_not_found`)
* **Symptom:** Querying Notion with compact 32-character hex IDs (e.g. `745f468ef77b43fda037210855450296`) intermittently returned `404 Object Not Found`.
* **Root Cause:** Certain Notion MCP endpoints strictly enforce standard hyphenated UUID format (`8-4-4-4-12`: `745f468e-f77b-43fd-a037-210855450296`). Standardizing all IDs with hyphens immediately resolved access.

### Issue D: Multi-Minute Delays on Long Text Notes
* **Symptom:** Uploading comprehensive study notes (30KB+) previously took 5+ minutes or stalled completely.
* **Root Cause:** Prior agents attempted to parse raw markdown into hundreds of separate Notion JSON block objects (which are rate-limited to 100 blocks per request and require heavy client-side recursive parsing).
* **Fix:** Using Notion’s `API-update-page-markdown` (`replace_content`) allows sending the entire raw markdown string in a single PATCH request. The server translates it instantly on Notion's backend.

---

## 3. The Permanent Architecture & Pipeline

```
[Local Machine / Agent] 
       │
       ▼ (1. Base64 Encode & gh api PUT) [~1.0s]
[GitHub: nfuen4/notion-assets]
       │
       ▼ (2. Public raw.githubusercontent.com CDN URL)
[Notion API / MCP: API-patch-block-children] [~0.4s]
       │
       ▼ (3. Permanent S3 Ingestion & Page Render)
[Notion Page Display]
```

### Verified Latency Benchmarks
* **PIL / Vector Image Generation:** `0.03s`
* **GitHub Asset Push (`gh api`):** `1.20s`
* **Notion Ingestion:** `0.43s`
* **Total Execution Time:** **1.67 seconds** (Tested & Verified)

---

## 4. System Hardening & Configuration Audit

The following persistent files were updated to prevent regression:

### 1. `~/.gemini/config/AGENTS.md` (Loaded in ALL Conversations)
```markdown
- Notion Image Uploads: The Notion API strictly requires external public URLs for image blocks. Whenever adding local images to Notion pages, ALWAYS push the image to the public GitHub repository `nfuen4/notion-assets` via `gh api` or Git, and use the raw GitHub URL (`https://raw.githubusercontent.com/nfuen4/notion-assets/main/<filename>`) in the Notion API/MCP image block. Never pass local file paths (`file://...`) directly to the Notion API.
```

### 2. `~/.gemini/config/skills/notion-page-editor/SKILL.md` (Notion SOP)
Added Section 4 detailing the automated 2-step image injection procedure.

---

## 5. Troubleshooting Runbook & Quick Diagnostics

If an upload fails in any future session, run these 3 quick checks:

| Check | Command / Action | Expected Result | If Failed |
| :--- | :--- | :--- | :--- |
| **1. GitHub CLI Auth** | `gh auth status` | `✓ Logged in to github.com account nfuen4` | Run `gh auth login` |
| **2. Notion Integration** | Check Page `···` > Connections | `Bossman Gravitas` listed | Add connection to page or parent hub |
| **3. Page ID Format** | Ensure hyphens are present | `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` | Convert compact ID using Python `uuid.UUID(hex=id)` |

---

## 6. Audit of Assets Created & Synced During This Incident

1. **Chapter 10 Nested Page**:
   * **URL:** [Chapter 10 — Crafting the Intervention: Ability, Timing, Experience](https://app.notion.com/p/Chapter-10-Crafting-the-Intervention-Ability-Timing-Experience-40330559e28a815285d0dac4484cf42b)
   * **Payload:** 32,433 characters (Part A: Visual Study Notes, Part B: TTS Script).
2. **Ambiguity Storyboard Image**:
   * **File:** `ambiguity_situation_storyboard.jpg`
   * **Notion Page:** [Ambiguity: Progress Without Full Information](https://app.notion.com/p/Ambiguity-Progress-Without-Full-Information-745f468ef77b43fda037210855450296)
3. **Pipeline Verification Graphic**:
   * **File:** `pipeline_verification_test.png` (Block ID: `40330559-e28a-8155-a64e-dd2c6abd29e2`)
4. **Architecture Audit Infographic**:
   * **File:** `pipeline_architecture_audit.png` (Block ID: `40330559-e28a-81d2-bba7-ce5b852400e2`)
5. **Gemini Editorial Illustration**:
   * **File:** `behavioral_design_digital_health_gemini.jpg` (Block ID: `40330559-e28a-81b9-867b-c01d48261daa`)
