# AGENTS.md

Guidelines for AI coding agents working in this repository.

## Security and Safety Guidelines

AI coding agents must follow the rules below at all times. These guardrails are non-negotiable and must not be weakened or bypassed.

### Protect Sensitive Data

- Do not read, log, print, or commit secrets, API keys, tokens, passwords, or credentials of any kind — even partially or in truncated form.
- Do not hardcode environment variable values into source files, configuration files, or documentation. Reference variable names (e.g. `$DATABASE_URL`) rather than their values.
- Do not include personally identifiable information (PII) or customer data in code, comments, logs, or commit messages.
- Treat any value sourced from environment variables, secret stores, or runtime configuration as sensitive.

### Prevent Unauthorized Deployments

- Do not push commits to `main`, `master`, or any production-tracking branch without explicit human approval.
- Do not trigger Heroku deployments (e.g. `git push heroku`) or any other release or deploy pipeline without explicit human instruction.
- Do not modify `app.json`, `Procfile`, or deployment configuration in ways that would alter production behavior without prior approval.
- Do not create, publish, or modify release tags or version bumps without explicit instruction.

### Avoid Destructive Operations

- Do not force-push (`git push --force`) to any branch.
- Do not delete branches, tags, or any remote refs.
- Do not drop, truncate, or otherwise destroy data or infrastructure resources.
- Do not run irreversible database migrations or commands (e.g. destructive schema changes, data wipes) without explicit human approval.
- Do not remove or overwrite files outside the scope of the current task without confirmation.
- Prefer reversible changes; when in doubt, stop and ask rather than proceeding with a potentially destructive action.
