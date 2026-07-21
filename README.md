# Datasworn Community Content

This repository builds org-supported Datasworn community content into separate
npm package artifacts with `@datasworn-community/build-tools`.

The repo starts with migrated source data for:

- Starsmith
- Fe-Runners
- Ironsmith
- Ancient Wonders

Packages are configured for public publication under the
`@datasworn-community` npm scope. Use experimental PR publishes first to verify
package artifacts before relying on the stable main-branch release.

## Raw JSON

Generated raw Datasworn JSON is committed in `generated-datasworn/` for users
who want to download or browse files directly from GitHub.

Use `generated-datasworn/manifest.json` to see the current generated file,
package name, schema line, license, and dependency metadata for each content
package.

## Quick Start

```sh
bun install
bun run build
bun run validate
```

Generated artifacts are written to:

- `generated-datasworn/<package>.json`
- `datasworn/<package>/<package>.json`
- `dist/packages/<package>/`

Each `dist/packages/<package>` directory is an npm package artifact generated
by build-tools. Do not edit generated files by hand; edit `source_data/` and
`datasworn.config.yaml`, then rebuild.

## Packages

| Package ID | npm package | Dependency | Status |
|---|---|---|---|
| `starsmith` | `@datasworn-community/starsmith` | Starforged | Ready for experimental publish |
| `fe_runners` | `@datasworn-community/fe-runners` | Starforged | Ready for experimental publish |
| `ironsmith` | `@datasworn-community/ironsmith` | Ironsworn Classic, Delve | Ready for experimental publish |
| `ancient_wonders` | `@datasworn-community/ancient-wonders` | Starforged | Ready for experimental publish |

See [Packages](docs/PACKAGES.md), [Tier Policy](docs/TIER_POLICY.md), and
[Community Index](docs/COMMUNITY_INDEX.md) for Phase 4 tracking.

## Documentation

- Datasworn core and build-tools:
  <https://github.com/datasworn-community/datasworn>
- Official content examples:
  <https://github.com/datasworn-community/official-content>
- Shared content workflows:
  <https://github.com/datasworn-community/.github>
- Published npm packages:
  <https://www.npmjs.com/org/datasworn-community>

Project notes:

- [Packages](docs/PACKAGES.md)
- [Tier Policy](docs/TIER_POLICY.md)
- [Community Index](docs/COMMUNITY_INDEX.md)
- [Content Authoring](docs/CONTENT_AUTHORING.md)
- [Publishing](docs/PUBLISHING.md)
- [Provenance](PROVENANCE.md)

## Repository Layout

```text
source_data/           Datasworn source YAML you edit
datasworn.config.yaml  Build and package metadata
generated-datasworn/   Generated raw JSON committed for GitHub users
datasworn/             Generated built JSON, ignored by git
dist/packages/         Generated npm package artifacts, ignored by git
.github/workflows/    Build and release workflow callers
```

## How Publishing Works

The shared release workflows compare generated package artifacts against the
latest published version on the same Datasworn schema line. Changed packages are
published; unchanged packages are skipped.

Experimental canaries are enabled by applying the `release_experimental` label
to a pull request. Removing the label stops future publishes. The per-PR
dist-tags remain after the PR closes as convenience aliases; use the exact
canary version from the PR comment for reproducible installs.

Before publishing, read [Publishing](docs/PUBLISHING.md).

## Contributing

Org-wide conventions — where to open PRs, release labels, shared CI — live in the [Datasworn Community CONTRIBUTING guide](https://github.com/datasworn-community/.github/blob/main/CONTRIBUTING.md).
