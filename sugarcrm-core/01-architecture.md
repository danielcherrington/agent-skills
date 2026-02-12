# Sugar 25 Architecture & Platform Best Practices

## Platform stack (Sugar 25)

- **Backend:** PHP (version per [Supported Platforms](https://support.sugarcrm.com/Resources/supported_platforms) for 25.x)
- **Frontend:** Sidecar — Backbone.js–based client; primary UI layer for Sugar 25
- **API:** REST API for integrations and headless access
- **Docs:** [Sidecar API](https://apidocs.sugarcrm.com/Sidecar/25.2.0/) and [DB Schema](https://apidocs.sugarcrm.com/schema/25.2.0/ent/) for your exact 25.x release

Always confirm the exact Sidecar and schema docs for the minor version you target (e.g. 25.1.0 vs 25.2.0).

## Sidecar (frontend) best practices

1. **Use Sidecar for new UI** — Sugar 25’s standard UI is Sidecar. Prefer views, layouts, and components in the Sidecar framework rather than legacy MVC.
2. **Reference versioned Sidecar docs** — Use [apidocs.sugarcrm.com](https://apidocs.sugarcrm.com/) for your 25.x build (e.g. 25.1.x or 25.2.0) so APIs and schema match your release.
3. **Extend, don’t replace** — Extend Sugar’s Sidecar views and models where possible instead of forking or replacing core files.
4. **Respect build and upgrade** — Custom JS/views should be packaged so they survive Quick Repair and upgrades (e.g. via MLP or documented extension points).

## Module and directory structure

1. **Custom modules** — Place new modules in `custom/` (or deliver via MLP). Do not add modules inside core `modules/` so upgrades stay clean.
2. **Naming** — Use a clear, unique prefix or namespace for custom modules and classes to avoid clashes with core and other packages.
3. **Module Loadable Packages (MLP)** — For anything you deploy or distribute, use MLPs so installations are consistent and reversible. Follow [SugarCRM Marketplace Package Guidelines](https://support.sugarcrm.com/smartlinks/developer_guide/architecture/module_loader/sugar_exchange_package_guidelines/) if targeting Marketplace or multiple tenants.

## Module Loadable Packages (MLP)

- **Use for:** New modules, major customizations, and anything installed on multiple instances or shared (e.g. Marketplace).
- **Benefits:** Install/uninstall without editing core, clearer upgrade path, and alignment with Sugar’s packaging and Cloud policies.
- **Requirement for Marketplace:** Marketplace add-ons must follow the [Marketplace Package Guidelines](https://support.sugarcrm.com/smartlinks/developer_guide/architecture/module_loader/sugar_exchange_package_guidelines/).

## Supported platforms

- **Check per release** — Supported PHP, database, and OS versions change by release. For Sugar 25, use the [Supported Platforms](https://support.sugarcrm.com/Resources/supported_platforms) page for your exact 25.x version.
- **Dev/test/prod parity** — Keep development, test, and production on supported platform combinations to avoid surprises at upgrade and go-live.

## Summary

- Build UI in Sidecar; use versioned Sidecar and schema docs for 25.x.
- Put customizations in `custom/` or in MLPs; avoid editing core.
- Use MLPs for distributable or installable work; follow Marketplace guidelines if publishing.
- Run only on supported platforms for your target 25.x release.
