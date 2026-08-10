# Assistant Notebook for ChatGPT and Codex

## What problem does it solve?

When you work with ChatGPT for a long time, important information becomes scattered across different conversations. A chat may become too long, you may start a new one, or ChatGPT may no longer have all the details immediately available.

Assistant Notebook gives ChatGPT a simple working notebook in ChatGPT Library.

Before doing important work, ChatGPT opens the notebook and checks what was done previously. During the task, it records useful results, decisions, files, problems, and next steps. This helps ChatGPT continue work without asking you to explain the whole project again.

The notebook is useful for:

- long-running projects;
- job searches and applications;
- company research;
- legal and administrative matters;
- plans and recurring tasks;
- any work that continues across multiple conversations.

The skill does not copy your complete chat history. It keeps only short working notes that may be useful later. It also tells ChatGPT not to store passwords, API keys, authentication tokens, or other secrets in the notebook.

## What do I need?

- ChatGPT or Codex with personal Skills support;
- ChatGPT Library.

## Install and configure it

You do not need to download files or understand how skills work.

Copy the complete text below, paste it into ChatGPT, and send it:

```text
Install and configure Assistant Notebook for me.

The skill is located here:
https://github.com/pickleshell/skills/tree/main/assistant-notebook

Use the skill-creator workflow to download, validate, and install assistant-notebook as my personal skill. Do not modify the skill.

After installation, use $assistant-notebook to create my primary Assistant Notebook in ChatGPT Library. Create one folder named Assistant Notebook, one index file named Assistant Notebook - Contents.md, and one Notebook Protocol.md page. Ask me what projects or areas I want to keep in the notebook before creating any subject pages. Create only the pages I actually need.

Do not copy my complete conversation history, passwords, API keys, tokens, government identifiers, or other secrets into the notebook.

When everything is ready, tell me which notebook pages were created and confirm that assistant-notebook is installed and available in my Skills directory.
```

ChatGPT will install the skill, ask what you want to track, and create the initial notebook pages for you.

## How do I use it afterward?

Use ChatGPT normally. The skill is designed to open the notebook automatically before meaningful work and update it after important progress.

If you want to invoke it explicitly, write:

```text
Use $assistant-notebook, restore the context for this project, and tell me the current status and next step.
```

You can also ask:

```text
Use $assistant-notebook and show me what projects and open tasks are currently in my notebook.
```

The operational instructions used by ChatGPT are in [`SKILL.md`](SKILL.md).
