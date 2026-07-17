# Packages

This repo is the shared home for org-supported Datasworn community content.
Each source package builds to its own npm package artifact under
`dist/packages/`.

All packages publish publicly under the `@datasworn-community` npm scope. Use
experimental PR publishes (`release_experimental` label) to verify canary
artifacts before merging changes that ship to the stable npm dist-tag.

| Package ID | npm Package | Author | Dependency | License | Status |
|---|---|---|---|---|---|
| `starsmith` | [`@datasworn-community/starsmith`](https://www.npmjs.com/package/@datasworn-community/starsmith) | Eric Bright | `@datasworn-community/starforged` | CC-BY-4.0 | Published |
| `fe_runners` | [`@datasworn-community/fe-runners`](https://www.npmjs.com/package/@datasworn-community/fe-runners) | Craig Smith | `@datasworn-community/starforged` | CC-BY-NC-SA-4.0 | Published |
| `ironsmith` | [`@datasworn-community/ironsmith`](https://www.npmjs.com/package/@datasworn-community/ironsmith) | Eric Bright | `@datasworn-community/ironsworn-classic`, `@datasworn-community/ironsworn-classic-delve` | CC-BY-4.0 | Published |
| `ancient_wonders` | [`@datasworn-community/ancient-wonders`](https://www.npmjs.com/package/@datasworn-community/ancient-wonders) | Ludic Pen | `@datasworn-community/starforged` | CC-BY-NC-SA-4.0 | Published |

## Adding a new package

The checklist below applies when adding a new source package to this repo,
before its first stable publish:

1. Record author outreach and response (or note the license terms under which
   the content is being redistributed).
2. Confirm the package's tier per [`TIER_POLICY.md`](./TIER_POLICY.md).
3. Confirm a named maintainer for Tier 2 packages.
4. Confirm the configured npm package name and license.
5. Confirm `bun run build` and `bun run validate` pass.
6. Apply `release_experimental` to the initial PR and verify canary artifacts
   before merging to `main`.
