# Skills

Reusable skills for ChatGPT and Codex.

## Assistant Notebook

`assistant-notebook` gives ChatGPT a persistent working notebook in ChatGPT Library.

Long conversations can be shortened, interrupted, or continued in a new chat. Important details may then become difficult to recover. This skill teaches ChatGPT to use a small set of text pages in Library as a working notebook:

- open the notebook before starting meaningful work;
- read only the page relevant to the current task;
- combine notebook information with the current conversation;
- verify current facts instead of blindly trusting old notes;
- record important results, decisions, blockers, files, and next steps;
- keep passwords, tokens, and other secrets out of the notebook.

The notebook does not replace the conversation and does not export chat history. It stores only concise working information that will be useful later.

Typical uses include long-running projects, job searches, company research, applications, legal or administrative work, plans, and recurring technical tasks.

### Requirements

- ChatGPT or Codex with personal Skills support;
- ChatGPT Library enabled.

### Install it with ChatGPT

Copy the request below into ChatGPT:

```text
Install the assistant-notebook skill from this GitHub repository:
https://github.com/pickleshell/skills/tree/main/assistant-notebook

Use the skill-creator workflow to download, validate, and install it as my personal skill. Do not modify the skill. After installation, confirm that assistant-notebook is available in my Skills directory.
```

### Create your notebook

After the skill is installed, send this request:

```text
Use $assistant-notebook to set up my primary Assistant Notebook in ChatGPT Library.

Create one folder named Assistant Notebook, one index file named Assistant Notebook - Contents.md, one Notebook Protocol.md page, and only the minimum subject pages needed for my current work. Ask me what areas I want to track before creating subject pages. Do not copy my conversation history, passwords, tokens, or other secrets into the notebook.
```

After that, use ChatGPT normally. The skill is designed to check the notebook automatically before substantive work and update it after meaningful progress.

You can also invoke it explicitly:

```text
Use $assistant-notebook, restore the context for this project, and tell me the current status and next step.
```

Skill source: [`assistant-notebook/SKILL.md`](assistant-notebook/SKILL.md)
