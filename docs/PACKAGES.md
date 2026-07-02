# Packages

This repo is the shared home for org-supported Datasworn community content.
Each source package builds to its own npm package artifact under
`dist/packages/`.

All packages are configured for public publication under the
`@datasworn-community` npm scope. Use experimental PR publishes to verify the
first artifacts before stable publication from `main`.

| Package ID | npm Package | Author | Dependency | License | Status |
|---|---|---|---|---|---|
| `starsmith` | `@datasworn-community/starsmith` | Eric Bright | `@datasworn-community/starforged` | CC-BY-4.0 | Ready for experimental publish |
| `fe_runners` | `@datasworn-community/fe-runners` | Craig Smith | `@datasworn-community/starforged` | CC-BY-NC-SA-4.0 | Ready for experimental publish |
| `ironsmith` | `@datasworn-community/ironsmith` | Eric Bright | `@datasworn-community/ironsworn-classic`, `@datasworn-community/ironsworn-classic-delve` | CC-BY-4.0 | Ready for experimental publish |
| `ancient_wonders` | `@datasworn-community/ancient-wonders` | Ludic Pen | `@datasworn-community/starforged` | CC-BY-NC-SA-4.0 | Ready for experimental publish |

## First Publish Checklist

Before relying on stable publication from `main`:

1. Record author outreach and response.
2. Confirm the package's tier.
3. Confirm a named maintainer for Tier 2 packages.
4. Confirm the configured npm package name and license.
5. Confirm `bun run build` and `bun run validate` pass.
6. Apply `release_experimental` to the initial PR and verify canary artifacts.
