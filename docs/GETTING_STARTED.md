# Getting Started

This checklist gets the community content repo to a successful local build.

## 1. Install Tools

Install Bun 1.3 or newer:

```sh
bun --version
```

Then install dependencies:

```sh
bun install
```

## 2. Review Package Config

Package metadata lives in `datasworn.config.yaml`:

- `repository.url`: the GitHub repository URL.
- `packages[].id`: the Datasworn package ID, such as `starsmith`.
- `packages[].source`: the matching source directory.
- `packages[].packageName`: the npm package name.
- `packages[].description`: the generated package description.
- `packages[].license`: the generated package license.

Keep package IDs lowercase with underscores and npm package names lowercase with
hyphens.

## 3. Choose Dependencies

Starforged expansions use:

```yaml
dependencies:
  - starforged
publishDependencies:
  - id: starforged
    packageName: "@datasworn-community/starforged"
    schemaLine: "0.2"
```

Keep `@datasworn-community/starforged` in `devDependencies` when your source
references Starforged IDs. For Ironsworn Classic content, use
`@datasworn-community/ironsworn-classic` instead and update the dependency ID to
`classic`.

If your package is a standalone ruleset, change `type` to `ruleset`, remove
`ruleset: starforged` from source YAML, and remove the dependency declarations.

## 4. Build and Validate

```sh
bun run build
bun run validate
```

The build fails if:

- source YAML is invalid;
- referenced Datasworn IDs cannot be resolved;
- package versions do not match the configured schema line;
- required package metadata, such as `repository`, is missing.

## 5. Prepare to Publish

Before relying on stable publication from `main`:

1. Confirm `packageName` is the package the org intends to publish.
2. Confirm `repository.url` points at this repository.
3. Confirm licenses and provenance docs are accurate.
4. Open a PR and apply `release_experimental`.
5. Verify canary artifacts.
6. Read [Publishing](PUBLISHING.md).
