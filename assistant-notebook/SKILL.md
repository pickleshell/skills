---
name: assistant-notebook
description: Consult and maintain the user's persistent Assistant Notebook in ChatGPT Library. Use before every substantive work task, including when the current conversation appears complete, as a preventive checkpoint against context loss. This includes projects, job search, companies, applications, files, legal or administrative matters, plans, decisions, TODOs, and any request whose correctness may depend on prior work. Also use during and after meaningful progress to record verified outcomes, decisions, files, blockers, and next steps.
---

# Assistant Notebook

Use ChatGPT Library as the persistent working notebook. Do not copy or export ChatGPT conversation history or personal memory into it.

## Before work

Consult the notebook before every substantive work task, even when the active conversation already seems to contain sufficient context. Treat this as a preventive continuity checkpoint, not only as recovery after confusion or context loss.

1. Search Library by the exact title `Assistant Notebook - Contents.md`.
2. Read the contents page; never rely on a search snippet alone.
3. Follow its routing table and read only the relevant notebook page or pages.
4. Reconcile the relevant notebook information with the active conversation and other currently available context as two potentially unsynchronized sources; merge them without assuming either one is complete. Never replace or narrow the current context to what the notebook contains.
5. Treat notebook entries as orientation, not proof that an external action succeeded. Verify repositories, services, forms, correspondence, or source files when factual completion matters.
6. Expect the common case that recent discussion or progress exists in the active context but was not written to the notebook. Use it for the task and add durable missing information to the appropriate page as soon as the gap is noticed, including during the task rather than waiting until the end.
7. Resolve discrepancies by recency, specificity, status, and evidence rather than a blanket source priority. Verified current evidence wins. If a discrepancy cannot be resolved safely, preserve the uncertainty instead of silently overwriting either account.

If the contents page is unavailable, say so briefly and continue from verified available context. Do not create a second notebook automatically.

## During and after work

Update the relevant existing page after meaningful progress. Record concise, durable facts:

- confirmed result and date;
- decision and important rationale;
- current status or blocker;
- exact Library filename or folder for related artifacts;
- next action;
- evidence or verification source when useful.

Keep planned, attempted, and completed actions explicitly distinct. Mark replaced information as superseded instead of silently leaving contradictions. Preserve unrelated page content and Library file identity/version history.

Update `Assistant Notebook - Contents.md` only when adding, renaming, or removing a page, or when its one-line status summary changes materially. Do not use it as an activity log.

## Notes and artifacts

- Store resumes, company materials, project documents, and correspondence in the relevant Library folder.
- Refer to attachments by exact Library filename and folder; do not embed large file contents into notes.
- Prefer one maintained page per stable subject over many timestamped fragments.
- Never store passwords, API keys, authentication tokens, recovery codes, government identifiers, or other secrets in the notebook.
- Do not record casual conversation, transient reasoning, or facts already represented adequately by an attached source file.

## Write discipline

Use the OpenAI Library skill for every Library read or write. Search and read before replacing a page. Replace the same `library_file_id`; never create a duplicate merely because a local edit produced a new path. Use version guards when the current version is known, and reconcile version conflicts before retrying.
