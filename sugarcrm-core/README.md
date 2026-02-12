# SugarCRM Core Skill

Development best practices for **SugarCRM version 25** (Sugar 25.x). Use this skill when building or customizing Sugar (Sugar Sell, Sugar Serve, Sugar Enterprise) to stay aligned with official architecture, APIs, and policy.

## Scope

- **Target version:** Sugar 25.x (25.0, 25.1, 25.2)
- **Stack:** PHP backend, Sidecar (Backbone/JavaScript) frontend, REST API
- **References:** [Sugar Developer Guide 25.1](https://support.sugarcrm.com/documentation/sugar_developer/sugar_developer_guide_25.1/), [API Docs](https://apidocs.sugarcrm.com/), [Developer Policy](https://support.sugarcrm.com/Resources/Developer_Policy/)

## Contents

| Document | Purpose |
|----------|---------|
| [01-architecture.md](01-architecture.md) | Platform stack, Sidecar, module structure, Module Loadable Packages (MLP) |
| [02-customization.md](02-customization.md) | Logic hooks, API usage, REST, and extension points |
| [03-code-standards.md](03-code-standards.md) | PHP/JS conventions, security, and upgrade-safe patterns |
| [04-developer-policy.md](04-developer-policy.md) | Policy, supported platforms, and Marketplace/MLP requirements |

## Quick principles

1. **Prefer configuration and extension over core edits** — use Studio, logic hooks, and MLPs instead of changing core files.
2. **Target Sidecar for UI** — Sugar 25 uses the Sidecar (Backbone.js) client; avoid relying on legacy MVC where possible.
3. **Package with MLP for distribution** — use Module Loadable Packages for installable, upgrade-safe customizations.
4. **Stay on supported platforms** — keep PHP, DB, and OS within [Supported Platforms](https://support.sugarcrm.com/Resources/supported_platforms) for your release.
5. **Follow Developer Policy** — no forking, no prohibited licenses (e.g. GPL/AGPL), no stripping of Critical Control Software or Sugar notices.
