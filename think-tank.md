# Think Tank

Tech discoveries from Ray's #inspiration feed. Newest entries first.

---

## QMD: Local Hybrid Search Engine
**Date:** 2026-02-24  
**Source:** https://github.com/tobi/qmd

**What it is:**  
Local markdown search engine combining BM25 full-text search, vector embeddings, and LLM re-ranking. Runs entirely locally via node-llama-cpp with GGUF models (~2GB total). Built-in MCP server for Claude Desktop and Claude Code integration. Smart chunking (900 tokens with semantic boundary detection), query expansion, and RRF fusion scoring.

**Core principle:**  
**Hybrid search beats any single approach.** BM25 finds exact matches, vectors find semantic similarity, query expansion catches variations, and LLM reranking adjusts for context. Position-aware blending (75% retrieval / 25% reranker for top results) prevents the reranker from destroying high-confidence exact matches. Local execution = no API costs, no privacy concerns.

**How this could apply to our work:**  
**Recall** should adopt the same hybrid approach for session search: BM25 for exact code/error matches, vectors for "find sessions about auth", reranking for relevance. QMD's "context" system (qmd://notes → "Personal notes and ideas") maps perfectly to Recall's team/project metadata. MCP server pattern is already what we're building. **Consider:** Could we embed QMD directly in Recall as the search backend, or learn from its chunking/scoring algorithms?

**Ray's comment:**  
"that qmd one is a big one that we need for sure!"

---

## Mobile UI Patterns for Agents (OpenClaw Compatible)
**Date:** 2026-02-24  
**Source:** https://x.com/aaronabentheuer/status/2025949178744979749

**What it is:**  
Open source library of UI patterns for agents on mobile, starting with Live Activities for observability. Built by Aaron Abentheuer, compatible with OpenClaw.

**Core principle:**  
**Agents need mobile-native UI, not just desktop.** Live Activities (iOS) provide persistent, glanceable status for long-running agent tasks. This is observability as a first-class mobile experience, not a web dashboard you have to open.

**How this could apply to our work:**  
**Recall** sessions could push Live Activity updates: "Building feature X... 3/5 tests passing... PR ready for review." **Keeper** fleet alerts via Live Activities: "Fraud alert: Vehicle #1234 - unusual mileage spike." **OpenClaw** could standardize mobile agent patterns across all products. Mobile-first observability is a competitive edge — most AI tools are desktop-only.

**Ray's comment:**  
_(none — bare URL share)_

---

## Exa Web Search + Claude Code Integration
**Date:** 2026-02-24  
**Source:** https://x.com/garrytan/status/2025585446559097288

**What it is:**  
Garry Tan sharing how to integrate Exa web search with Claude Code. In plan mode, say "I want to use Exa", brainstorm where agents use it, exit plan mode, enter API key, and agents can search the web.

**Core principle:**  
**Agentic tools should make integration frictionless.** No config files, no code changes — just "I want to use X" in natural language, and the agent figures out how to wire it up. The agent designs its own tool usage pattern ("where should I search? when?") instead of you prescribing it.

**How this could apply to our work:**  
**Recall** could support "I want to use GitHub API" → agent generates MCP tool bindings automatically. **OpenClaw** could detect when a user mentions a service ("check Stripe for failed payments") and offer to integrate it on the fly. Natural language configuration = lower barrier to extending agent capabilities.

**Ray's comment:**  
_(none — bare URL share)_

---

## Ironclaw: Local AI CRM
**Date:** 2026-02-24  
**Source:** https://ironclaw.sh/

**What it is:**  
AI CRM hosted locally on your Mac. Minimal web presence (just ASCII art logo), suggesting early-stage or stealth product.

**Core principle:**  
**Local-first AI tools are a category.** Not everything needs to be cloud/SaaS. Privacy-sensitive workloads (CRM = customer data) benefit from on-device processing. Similar to Recall's local MCP server approach.

**How this could apply to our work:**  
**Recall** is already local-first via MCP. We should emphasize this in positioning: "Your team's knowledge stays on your machines, not in our cloud." **Keeper** could offer a local deployment option for fleets with strict data policies. Local-first = competitive advantage in regulated industries (healthcare, finance, automotive).

**Ray's comment:**  
_(none — bare URL share)_

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
