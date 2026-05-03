# GitHub Codespaces Setup

This fork is prepared to run Open Design in GitHub Codespaces without touching
any adjacent local repositories.

## First start

The devcontainer uses Node 24, enables Corepack, activates `pnpm@10.33.2`,
installs the Codex CLI, and runs `pnpm install`.

After the Codespace finishes creating, authenticate Codex with the same ChatGPT
account used for the Pro subscription:

```bash
codex login --device-auth
codex login status
```

Do not use API-key login for the default Synflow workflow unless a task
explicitly needs API billing instead of ChatGPT/Codex usage limits.

## Run Open Design

Use the single supported lifecycle entrypoint:

```bash
OD_HOST=0.0.0.0 OD_BIND_HOST=0.0.0.0 OD_CODEX_DISABLE_PLUGINS=1 pnpm tools-dev run web --daemon-port 7457 --web-port 5175
```

If fixed ports are already occupied, omit the port flags and use the forwarded
port that Codespaces reports:

```bash
OD_HOST=0.0.0.0 OD_BIND_HOST=0.0.0.0 OD_CODEX_DISABLE_PLUGINS=1 pnpm tools-dev run web
```

Open the forwarded web port shown by Codespaces. The daemon ports are forwarded
for health checks and app-to-daemon traffic.

## CoastKey sandbox rule

Do not mount or add `/workspaces/portfolio-cases` or any local
`portfolio-cases` checkout as an Open Design project directory. CoastKey work
inside this fork must use only:

- `design-systems/coastkey/DESIGN.md`
- `skills/coastkey-surface-prototype/`
- `skills/coastkey-template/`
- short, user-provided reference snippets

Accepted Open Design outputs can be reviewed manually and only then moved into
`portfolio-cases` through its normal implementation workflow.
