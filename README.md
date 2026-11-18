# Colortyme content catalog

This static catalog is a list of bundles, currently empty. Serve this directory as the document root of any reachable HTTP(S) endpoint and set the app build property `catalogUrl` to the served `catalog.json` URL. `catalog.json` lists bundles; each entry's `manifest` is a `bundle.json` whose page `image` paths are relative to it.

## Generated-bundle prototype

The local-only `coloring-bundle` skill (`.agents/skills/coloring-bundle`, excluded from Git via `.git/info/exclude`)
lets a Pi agent generate and review a four-page coloring collection, then prepare
A4 SVGs and a vector PDF. In Pi, run `/reload`, then for example:

```text
/skill:coloring-bundle Four friendly woodland animal pages for ages 5–7
```

The skill pauses for human approval and uses Pi's image models rather than a
separate generation service. Its print helper and tests run locally; each
bundle is generated directly into `bundles/<name>/` (brief, notes, prompts, originals,
exports, `bundle.json`), registered in `catalog.json`, and published by a pull request. The skill does not touch git.
See the skill README for dependency setup and the export command.

## Rights and provenance

Each bundle's `bundle.json` records per-page rights and provenance; every bundle needs its own source and redistribution-rights review.
