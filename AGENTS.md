# Halo Skills Development Guide

## Project Structure

```
halo-skills/
├── skills/                   # All skills live here
│   └── skill-name/
│       └── SKILL.md          # Required - main skill file
├── AGENTS.md                 # Development guide (this file)
├── CLAUDE.md                 # Points to AGENTS.md
├── LICENSE
└── README.md
```

## Skill Scopes

| Skill | Scope |
|-------|-------|
| **halo-search** | Search and retrieve post content on Halo-powered websites via public REST API. |

## Writing Skills

### SKILL.md Structure

Every skill requires a `SKILL.md` with YAML frontmatter:

```markdown
---
name: skill-name
description: What this skill does. When to use it.
---

# Skill Title

## Instructions
...
```

### Required Metadata

| Field | Requirements |
|-------|-------------|
| `name` | Max 64 chars, lowercase letters/numbers/hyphens |
| `description` | Max 1024 chars, includes WHAT it does and WHEN to use it |

### Description Best Practices

- Write in third person
- Be specific and include trigger terms
- Include both WHAT and WHEN

```yaml
# Good
description: Search post content on Halo sites. Use when the user provides a Halo site URL and wants to search or find posts.

# Bad
description: Helps with Halo stuff.
```

### Core Principles

1. **Concise**: The context window is shared — every token competes for space. Only add what the agent doesn't already know.
2. **Under 500 lines**: Keep SKILL.md concise. Use separate reference files for detailed content.
3. **Progressive disclosure**: Essential info in SKILL.md, details in linked files (one level deep).
4. **Concrete examples**: Show actual API calls, real response structures, not abstract descriptions.

### Halo API Conventions

All Halo skills should follow these conventions:

- Use `{baseUrl}` as placeholder for the site URL
- Public API endpoints do not require authentication
- Use `curl` via Shell tool for API calls
- Parse and format JSON responses for readable output
- Always construct full URLs by combining `{baseUrl}` with API paths or permalinks

### Common Halo API Prefixes

| Prefix | Scope |
|--------|-------|
| `/apis/api.halo.run/v1alpha1/` | Core public API |
| `/apis/api.content.halo.run/v1alpha1/` | Content public API |

## Checklist for New Skills

- [ ] `SKILL.md` has valid frontmatter (`name` + `description`)
- [ ] Description includes WHAT and WHEN
- [ ] Body is under 500 lines
- [ ] Examples use concrete API calls and responses
- [ ] Consistent terminology throughout
- [ ] No time-sensitive information
- [ ] README.md updated with new skill entry
