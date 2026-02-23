# Think Tank

Tech discoveries from Ray's #inspiration feed. Newest entries first.

---

## System Prompts Leaked (AI Dev Tools)
**Date:** 2026-02-23  
**Source:** https://github.com/x1xhlol/system-prompts-and-models-of-ai-tools

**What it is:**  
GitHub repo collecting leaked/reverse-engineered system prompts from major AI coding tools: Cursor, Devin AI, Claude Code, Windsurf, and ~20 others. 116k stars, 48k views.

**Core principle:**  
Every AI coding tool auto-injects context (open files, cursor position, linter errors, git state) and has ephemeral memory systems (Cursor's `update_memory`, Claude Code's `TodoWrite`). **None persist across sessions or teams.** Code citation formats vary by tool (Cursor: ```startLine:endLine:path, Claude Code: path:line).

**How this could apply to our work:**  
**Recall** should format output to match the tool's expectations — code citations in their syntax, context in their injection format. Detect which tool is calling (via env vars / headers) and adapt. Position Recall as the **universal memory layer** that works with any AI coding tool. "Cursor has memory. It dies when you close the tab. Ours doesn't."

Feature spec created: `specs/context-format-adapters.md` (backlog, post-v3 launch).

**Ray's comment:**  
"That one is important to recall"

---

_Template for future entries:_

## [Short Descriptive Title]
**Date:** YYYY-MM-DD  
**Source:** [URL]

**What it is:**  
[2-3 sentences]

**Core principle:**  
[The transferable idea, NOT just "this tool does X"]

**How this could apply to our work:**  
[Specific connections to Recall, Velona, Keeper, Work.Golf, or OpenClaw]

**Ray's comment:**  
[If he added one when sharing]

---
