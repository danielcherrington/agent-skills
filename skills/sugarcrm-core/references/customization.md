# Sugar 25 Customization Best Practices

## Prefer configuration over code

1. **Studio first** — Use Admin → Studio to add fields, relationships, layouts, and basic logic before writing PHP or JavaScript.
2. **Logic hooks for server-side behavior** — When you need server-side logic (validation, defaulting, sync), use logic hooks in `custom/Extension` or inside an MLP rather than editing core files.
3. **Avoid core file edits** — Customizations in core directories are overwritten on upgrade. Keep all custom code under `custom/` or inside an MLP.

## Logic hooks

- **Location:** Registered via `custom/Extension/modules/<Module>/Ext/LogicHooks/` (or equivalent in an MLP). Sugar loads and merges these at upgrade/repair.
- **Use for:** Before-save/after-save validation, defaulting, calling external services, and keeping logic out of core.
- **Best practice:** One clear responsibility per hook; keep hooks thin and delegate to classes in `custom/` (or your package) for testability and reuse.

## REST API

- **Primary integration surface** — Use the [REST API](https://support.sugarcrm.com/Documentation/Sugar_Developer/Sugar_Developer_Guide_25.1/Integration/Web_Services/REST_API/) (and versioned Developer Guide for 25.x) for integrations, mobile, and headless access.
- **Version alignment** — API behavior and schema follow the Sugar version; use the REST API section of the Developer Guide for your 25.x release.
- **Authentication and limits** — Respect rate limits and auth (OAuth2/API keys) as documented; especially important on SugarCloud.

## Frontend (Sidecar) customization

- **Views and layouts** — Extend Sidecar views and use metadata/layouts so customizations survive Quick Repair and upgrades.
- **New components** — Implement as Sidecar views/components and register them so the build and loader pick them up (e.g. via MLP or documented extension mechanism).
- **Avoid global hacks** — Do not rely on patching core Sidecar files or undocumented globals; prefer extension points and proper registration.

## Upgrade safety

- **No core edits** — Any change under core `modules/`, `include/`, or core Sidecar assets can be overwritten. Keep changes in `custom/` or in an MLP.
- **Repair and rebuild** — After code or metadata changes, run Quick Repair and Rebuild (and clear caches as needed) so extensions and Sidecar are in sync.
- **Test on same minor version** — Validate customizations on the same 25.x minor (e.g. 25.1) and check release notes before upgrading to the next minor.

## Summary

- Use Studio and logic hooks before writing custom code; keep logic hooks small and delegate to your own classes.
- Use the REST API for integrations; follow the 25.x Developer Guide and respect auth/limits.
- Customize the frontend via Sidecar extension and metadata; avoid editing core Sidecar files.
- Keep all customizations in `custom/` or MLPs and test upgrades on supported platforms.
