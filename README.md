# halo-skills

Deprecated，See https://github.com/halo-dev/cli

Agent skills for interacting with websites built with [Halo](https://github.com/halo-dev/halo), an open-source CMS.

## Installation

```bash
npx skills add halo-sigs/halo-skills
```

## Usage

For most reliable results, prefix your prompt with `use halo skill`:

```
Use halo skill, search posts about "plugin development" on https://www.halo.run
```

This explicitly triggers the skill and ensures the AI follows the documented patterns.

## Available Skills

| Skill | When to use | Description |
|-------|-------------|-------------|
| **halo-search** | Search posts on a Halo site | Search and retrieve post content via Halo public API |

## About Halo

[Halo](https://github.com/halo-dev/halo) is a powerful open-source content management system (CMS). These skills leverage Halo's public REST API to enable AI agents to interact with any Halo-powered website without authentication.

## Contributing

1. Create a feature branch
2. Add your skill under `skills/your-skill-name/SKILL.md`
3. Update the Available Skills table in this README
4. Submit a PR

## License

MIT
