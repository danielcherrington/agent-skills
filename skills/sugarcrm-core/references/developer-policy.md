# Sugar 25 Developer Policy & Requirements

Developers building on Sugar 25 must follow [SugarCRM's Developer Policy](https://support.sugarcrm.com/Resources/Developer_Policy/). Summary of requirements and best practices:

## Use and purpose

- Use Sugar products and developer tools only for the purpose allowed by your agreement with Sugar (e.g. Developer License or other written agreement).
- Do not use or share Sugar for purposes outside that agreement.

## Supported platforms

- **Mandatory for on-prem / self-hosted** — Development and deployment must use [Supported Platforms](https://support.sugarcrm.com/Resources/supported_platforms) for your Sugar 25.x release.
- Supported platforms change by release; keep dev, test, and production environments on valid combinations (PHP, DB, OS, etc.).

## Intellectual property and trademarks

Unless Sugar has given explicit written permission, you must **not**:

- Share any part of Sugar with a competitor or use it to build a competitive product or copy its features or UI.
- Combine or use Sugar with code under a prohibited license (e.g. AGPL, GPL v3, Creative Commons, or similar "copyleft" licenses that could require disclosing Sugar source).
- Modify, remove, or disable any "Critical Control Software."
- Fork Sugar (take the source and start an independent product from it).
- Remove or alter SugarCRM/Sugar copyright, trademark, or proprietary notices.

## SugarCloud

- SugarCloud is shared; usage must follow the [SugarCloud Policy Guide](https://support.sugarcrm.com/Resources/sugar_cloud_policy_guide/).
- Custom code and integrations must operate within SugarCloud limits; violating code can be removed and banned from SugarCloud.

## Marketplace add-ons (MLPs)

For plug-ins or integrations published as [SugarCRM Marketplace](https://marketplace.sugarcrm.com/) add-ons:

- Follow the [SugarCRM Marketplace Package Guidelines](https://support.sugarcrm.com/smartlinks/developer_guide/architecture/module_loader/sugar_exchange_package_guidelines/) for [Module Loadable Packages](https://support.sugarcrm.com/smartlinks/developer_guide/cookbook/module_loadable_packages/) (MLPs).
- These guidelines help MLPs install safely and coexist with other customizations.
- Add-ons that do not follow the guidelines can be removed and banned from Marketplace and SugarCloud.

## Summary

- Use Sugar only as allowed by your agreement; run only on supported platforms for 25.x.
- Do not fork Sugar, use prohibited licenses, or remove/alter Critical Control Software or Sugar notices.
- Respect SugarCloud policy and limits for customizations and integrations.
- For Marketplace distribution, package as MLPs and follow the Marketplace Package Guidelines.
