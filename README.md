# Acendas Marketplace

A Claude Code plugin marketplace by [Acendas](https://acendas.ca). Curated developer-productivity plugins for spec-driven development, sprint management, and Atlassian Cloud integration.

## Plugins

| Plugin | Version | What it does |
|---|---|---|
| [`shipyard`](https://github.com/Acendas/shipyard) | 1.11.0 | Spec-driven agile sprint lifecycle for Claude Code — discuss features, plan sprints, build with TDD, review, and ship. |
| [`atlassian-suite`](https://github.com/Acendas/atlassian-suite) | 0.2.1 | Unified Jira Cloud + Confluence Cloud + Bitbucket Cloud integration. 190 MCP tools, 31 workflow skills, 21 agents including a 12-scanner PR review pipeline with adversarial critic. |

## Install

Add the marketplace once:

```
/plugin marketplace add Acendas/acendas-marketplace
```

Install plugins individually:

```
/plugin install shipyard@acendas
/plugin install atlassian-suite@acendas
```

List and update:

```
/plugin marketplace list
/plugin marketplace update
```

## Plugin sources

Each plugin lives in its own repository:

- `shipyard` — [`Acendas/shipyard`](https://github.com/Acendas/shipyard) (plugin path: `plugins/shipyard/`)
- `atlassian-suite` — [`Acendas/atlassian-suite`](https://github.com/Acendas/atlassian-suite) (flat repo)

Plugin-specific issues, PRs, and releases live in those repos. Use this repo only for marketplace-level issues (manifest errors, plugin listing changes, new plugins).

## License

MIT — see [LICENSE](./LICENSE).
