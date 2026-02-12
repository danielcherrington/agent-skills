# Sugar 25 Code Standards & Conventions

## PHP

- **Location** — All custom PHP under `custom/` (or inside an MLP). No persistent edits in `modules/`, `include/`, or `data/` core trees.
- **Naming** — Use descriptive class and method names; consider a prefix or namespace for your custom code to avoid collisions with core and other packages.
- **Sugar entry points** — Bootstrap via `sugarEntry` or the appropriate entry point; do not bypass Sugar’s bootstrap or assume global state from core.
- **DB and security** — Use Sugar’s DB layer and APIs; avoid raw SQL with user input. Validate and sanitize input; use parameterized queries where applicable.
- **Logic hooks** — Keep hook callbacks short; delegate to service or helper classes in `custom/` for clarity and reuse.

## JavaScript (Sidecar)

- **Framework** — Sidecar is Backbone.js–based. Follow patterns from existing Sidecar views/models and the [Sidecar API docs](https://apidocs.sugarcrm.com/Sidecar/25.2.0/) for your 25.x version.
- **APIs** — Use App.*, context, and metadata as intended; avoid relying on undocumented internals or private APIs that may change.
- **Registration** — New views/components should be registered so the build and loader include them; avoid ad-hoc script tags that break repair/upgrade.

## Security

- **Access control** — Rely on Sugar’s ACL and team/role model; do not bypass security checks in custom code or API usage.
- **Input** — Validate and sanitize all inputs; use Sugar’s APIs for DB access and file operations.
- **Secrets** — No credentials or API keys in repo or client-side code; use config/admin-defined settings and secure storage.

## Upgrade and compatibility

- **Deprecations** — Watch release notes and Developer Guide for deprecated APIs; plan migration before removal.
- **Supported platforms only** — Develop and run on [Supported Platforms](https://support.sugarcrm.com/Resources/supported_platforms) for your 25.x target.
- **Repair and rebuild** — After any code or metadata change, run Quick Repair and Rebuild so caches and extensions are correct.

## Summary

- Custom PHP and JS live in `custom/` or MLP; use Sugar’s DB and security layers; keep logic hooks thin.
- Sidecar code should follow official patterns and versioned APIs; register new components properly.
- Enforce security via ACL and input handling; no secrets in code.
- Stay on supported platforms and track deprecations for 25.x.
