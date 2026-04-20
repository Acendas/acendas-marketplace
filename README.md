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

After running `update`, reinstall any plugin to pick up its new pinned version.

## How it's versioned

Every plugin entry in this marketplace is pinned to a **version tag** — not a floating `main` branch. That means:

- Installs are deterministic. The plugin you get today is the same one anyone else installing today gets.
- Upstream pushes to `main` on a plugin repo **do not** auto-ship to installed users — a new release requires tagging the plugin repo *and* bumping the `ref` here.
- Rollback is a one-line edit: revert the `ref` in `.claude-plugin/marketplace.json`.

### Release workflow (for maintainers)

When a plugin is ready for release:

1. In the plugin repo, bump `version` in `.claude-plugin/plugin.json` and commit.
2. Tag the release: `git tag -a vX.Y.Z -m "..."` and `git push origin main vX.Y.Z`.
3. In this repo, update the plugin's entry in `.claude-plugin/marketplace.json` — bump `version` to match and change `source.ref` to the new tag.
4. Commit and push this repo.

Users run `/plugin marketplace update` to pick up the new ref, then `/plugin install <name>@acendas` to upgrade.

## Plugin sources

Each plugin lives in its own repository:

- `shipyard` — [`Acendas/shipyard`](https://github.com/Acendas/shipyard) (`source: git-subdir`, path: `plugins/shipyard/`)
- `atlassian-suite` — [`Acendas/atlassian-suite`](https://github.com/Acendas/atlassian-suite) (`source: github`, manifest at repo root)

## Issues and contributions

- **Plugin bugs or feature requests** → open an issue on the plugin's own repo (linked above). Plugin-specific code, tests, and releases live there.
- **Marketplace manifest errors, listing changes, new plugin submissions** → open an issue or PR on this repo.

## License

MIT — see [LICENSE](./LICENSE).
