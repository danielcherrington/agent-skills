# Agent Skills

A collection of reusable skills for AI coding agents.

## Available skills

### sugarcrm-core

SugarCRM 25.x development best practices: architecture (Sidecar, MLP), customization (logic hooks, REST API), code standards, and developer policy. Use when building or customizing Sugar (Sugar Sell, Sugar Serve, Sugar Enterprise).

**Use when:**
- Customizing or extending Sugar 25
- Writing logic hooks, REST integrations, or Sidecar UI
- Packaging modules (MLP) or targeting SugarCloud/Marketplace
- Reviewing Sugar code for upgrade safety and policy compliance

## Installation

Install all skills from this repo:

```bash
npx skills add danielcherrington/agent-skills
```

Install only one skill (e.g. sugarcrm-core):

```bash
npx skills add danielcherrington/agent-skills --skill sugarcrm-core
```

List available skills without installing:

```bash
npx skills add danielcherrington/agent-skills --list
```

## License

MIT
