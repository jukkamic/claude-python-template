# Python & Claude CLI Micro-Agent Template

A Devcontainer-ready workspace optimized for AI-driven development, strict environmental governance, and micro-agent orchestration using Anthropic's Claude CLI.

## Quick start

If you have the GitHub CLI (`gh`) installed, you can scaffold and clone a new project in one command:

```bash
gh repo create my-new-project --template your-username/your-template-repo-name --clone
cd my-new-project
```

## Architectural Philosophy

This template is built on a few core principles to maximize AI velocity while preventing token waste and system collapse:
* **Text-as-Infrastructure:** AI behavior is governed by plain-English markdown files (`CLAUDE.md`, `.claude/agents/*`) rather than heavy frameworks.
* **Micro-Agent Orchestration:** Complex tasks are broken down into small, deterministic, single-purpose Python scripts managed by specialized subagents.
* **Strict Environment Governance:** All dependencies are confined to a local `.venv` to prevent global bloat and infrastructure pollution.
* **Context Protection:** Secrets (`.env`) are hidden from the AI, and recursive directory ingestion is tightly controlled.
* **Stateful Execution:** Micro-agents are designed with memory (e.g., tracking processed items or previous error messages) to prevent redundant actions and notification spam.

## Features Included

* **VS Code Devcontainer:** Pre-configured with Python 3.13, Node.js (for Claude CLI), and Zsh.
* **Automated `.venv` Setup:** The virtual environment is built and mapped automatically upon container creation.
* **Linter Subagent:** Includes a `python-linter` agent powered by Ruff to handle code cleanup out-of-band.
* **Permissions Lockdown:** Pre-configured `.claude/settings.local.json` denies read/write access to `.env` files.

## z.ai for Claude

Configure ~/.claude/settings.json 

```bash
{
  "env": {
    "ANTHROPIC_AUTH_TOKEN": "your_zai_api_key",
    "ANTHROPIC_BASE_URL": "https://api.z.ai/api/anthropic",
    "API_TIMEOUT_MS": "3000000",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "glm-4.5-air",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "glm-4.7",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "glm-5"
  },
  "enabledPlugins": {
    "compound-engineering@compound-engineering-plugin": true
  },
  "extraKnownMarketplaces": {
    "compound-engineering-plugin": {
      "source": {
        "source": "github",
        "repo": "EveryInc/compound-engineering-plugin"
      }
    }
  },
  "shellSnapshotEnabled": false,
  "skipDangerousModePermissionPrompt": false
}
```

**Note:** skipDangerousModePermissionPrompt is set to false. If you run Claude explicitly in container you may want to change this to true. Container is, however, connected to host file system so be careful choosing your risk levels.