---
name: mem0-memory
description: Recall focused project context and preserve short, verified facts through the installed BOS-local Mem0 MCP. Use for explicit remember/recall requests, useful missing context when resuming work, and durable progress when memory writes are authorized. Coordinate with the Assistant Notebook as a retrieval index.
---

# Mem0 Memory

Use Mem0 for atomic facts and the Assistant Notebook for curated project routing.
Current user instructions and verified live evidence take precedence over both.
A skill does not authorize additional writes: respect read-only tasks, explicit
scope limits, and higher-priority instructions. Existing authorization and standing
preferences apply; do not ask again for an already authorized memory operation.

## Discover access and choose a target

- Before the first Mem0 operation in a session, call the installed
  `memory_capabilities` tool. The current BOS prefix is
  `mcp__bos_mem0_codex__`; discover the available tools if it is absent. Inspect
  backend health, supported operations, and permitted targets. Reuse this result
  during the session; refresh after a reconnect or an access/policy error.
- Use `memory_list_targets` when capabilities leave target selection unclear.
  Follow the live tool schemas rather than assuming a fixed argument list.
- Default to `target: "private"` when supported. Use a shared target only when the
  user has authorized sharing with that audience and the broker permits the
  operation. A shared target being available is not permission to publish private
  context there. Do not invent a target from a project name.
- Carry the selected target through search, add, get, update, history, and delete.
  Never pass raw `user_id`, `namespace`, `agent_id`, `principal`, or `scope` to
  override broker policy. Do not fetch credentials, bypass the broker, or widen
  access to recover from an error.

## Restore useful context

- When starting substantive work or resuming a project, consult the Assistant
  Notebook contents and relevant page once if available. Follow its pointers to
  source artifacts. Do not reread it before every message in the same context.
  An explicit Mem0 access check or a self-contained remember request need not
  trigger unrelated notebook retrieval.
- Search only for useful missing details: a focused `query`, normally `limit: 3`
  to `5`, and the selected target. Refine an unhelpful query before expanding it.
  Do not bulk-list memory or assume a particular model size or context capacity.
- Read exact records with `memory_get(memory_id, target)` when needed; use
  `memory_history` to resolve relevant changes. A similarity score is not proof
  of relevance or correctness. Empty results do not prove no prior work exists.
- Treat infrastructure paths, service state, commits, releases, and permissions
  as dated observations. Verify them live before relying on them for changes.

## Decide whether to write

| Situation | Action |
| --- | --- |
| User explicitly asks to remember | Save the requested durable facts within scope and verify before finishing. |
| Meaningful progress, with routine memory writes authorized | Save a durable decision, verified outcome, retrieval pointer, stable preference, or unresolved blocker with its resumption condition. |
| The same fact is already stored accurately | Do not write again. |
| New evidence supersedes the same fact | Update that record, including the verification date and relevant correction. |
| Only a related topic or a historical event matches | Keep its identity and history; add a distinct fact if useful. |
| Transient progress, speculation, raw logs, or redundant detail | Do not store it. |

Keep each record about one fact or decision. Include enough project/host context
to find it later, exact identifiers when useful, and a verification date for
changeable facts. Distinguish planned, attempted, and verified outcomes. Store a
pointer to a detailed report rather than copying the report or transcript.
Never store secrets, credentials, private raw logs, or unverified claims as facts.
Do not automatically copy notebook text into Mem0 or synchronize the two stores.
Update notebook routing only when a durable project decision/status or new source
pointer belongs there, following its own skill when available.

## Write and verify

1. Search the selected target for duplicates before an add or update. Inspect a
   candidate if its identity is uncertain. Update only the same fact; preserve
   unrelated information, deliberate handoff markers, and historical events.
2. Use `memory_add(text, infer: false, target)` for a new exact fact, or
   `memory_update(memory_id, text, target)` for a correction. For several facts,
   keep separate records rather than one long project summary.
3. Read each written record back with `memory_get` and compare the intended text
   and identifiers. If no ID is returned, search, inspect the matching record,
   and confirm its contents before claiming success.
4. For an important project decision or handoff, also search with a natural
   descriptive query to check discoverability. Exact-ID readback proves storage;
   semantic discovery is a separate check. If only the former succeeds, report
   that distinction instead of adding duplicate records.
5. Report what was saved and whether verification succeeded. Do not claim future
   recall is guaranteed. Delete records only within an authorized forget/cleanup
   request; verify absence in the same target.

## Failure handling

For an access/connectivity check, use capabilities and a bounded read; do not
create a test record unless a write test is requested. If a write times out or
has an ambiguous result, search/read before retrying to avoid duplicate writes.
Make only bounded retries, guided by the error. If access or persistence remains
unavailable, continue independent task work and state what was not saved or
verified. Do not silently fall back to another target, administrative access, or
a different persistent store.
