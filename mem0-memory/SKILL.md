---
name: mem0-memory
description: Use the installed BOS-local Mem0 MCP as focused associative/semantic memory for short atomic verified facts. When starting substantive work or resuming a project, consult the Assistant Notebook first when available, then use Mem0 only for useful missing details with bounded retrieval. Use when the user explicitly asks to remember something and after meaningful verified progress produces separate durable facts worth carrying into future sessions.
---

# Mem0 Memory

Treat Mem0 as a small retrieval layer alongside canonical repository documentation and the Assistant Notebook, never as their replacement or as authority for live system state.

Use the Assistant Notebook as the curated index for decisions, status,
retrieval cues, verified outcomes, blockers, and next steps. Do not copy it into
Mem0, automatically synchronize either direction, or write identical text to
both systems. After meaningful progress, keep any notebook update curated and
store only separate atomic facts here. For an explicit request to remember,
write and verify Mem0; update the notebook additionally only when the item is a
decision, status, or next step that belongs in its project index. Continue with
whichever mechanism remains available if the other fails. Current conversation
and verified live state override both.

## Retrieve

- At the start of substantive work or when restoring an old project, consult the Assistant Notebook first when available. If useful details are still missing, call `mcp__bos_mem0_codex__memory_search` with a focused `query` and a small `limit` (normally 3–5). Do not bulk-list or reread all memories.
- Keep retrieval bounded because BOS uses only tested 4B models; 8B models are unsuitable, and the 4B models also degrade with large context.
- Use `mcp__bos_mem0_codex__memory_get` with `memory_id` only when a returned record needs exact inspection. Use `mcp__bos_mem0_codex__memory_history` with `memory_id` when understanding how a fact changed matters.
- Verify relevant paths, commits, service state, and other live facts in the real system before risky or production actions.

## Store or update

- Before writing, call `mcp__bos_mem0_codex__memory_search` with a precise duplicate query and a small `limit`.
- If the durable fact already exists, call `mcp__bos_mem0_codex__memory_update` with its `memory_id` and the replacement `text`; do not create a near-duplicate. Otherwise call `mcp__bos_mem0_codex__memory_add` with concise `text` and normally `infer: false` so identifiers and technical facts remain exact.
- When the user explicitly says “remember” or “запомни,” perform the write synchronously, then verify availability with `mcp__bos_mem0_codex__memory_search` (or `mcp__bos_mem0_codex__memory_get` for the returned ID). Report honestly if persistence cannot be confirmed.
- After meaningful verified progress, automatically preserve only atomic durable facts: decisions with rationale, confirmed status, important paths/commits/IDs, blockers, next steps, and stable preferences.
- Never store secrets, API keys, tokens, credentials, private raw logs, large documents, whole conversations, unverified guesses, or transient noise.

## Scope and failure handling

- Let the server enforce scope. Never pass or attempt to override `user_id`, `namespace`, `agent_id`, or root/global scope; these are not valid tool arguments.
- Available tools are `mcp__bos_mem0_codex__memory_add(text, infer?)`, `memory_search(query, limit?)`, `memory_get(memory_id)`, `memory_list(limit?)`, `memory_update(memory_id, text)`, `memory_delete(memory_id)`, and `memory_history(memory_id)` under the same `mcp__bos_mem0_codex__` prefix.
- If the MCP is unavailable, continue the primary task. If persistence was explicitly requested, state that it was not confirmed.
