# Colortyme content catalog

This static catalog is a list of vector coloring-page bundles. Serve this directory as the document root of any reachable HTTP(S) endpoint and set the app build property `catalogUrl` to the served `catalog.json` URL.

## Catalog and bundle format

`catalog.json` lists published bundles:

```json
{
  "version": 1,
  "bundles": [
    {
      "id": "sea-creatures",
      "name": "Sea Creatures",
      "icon": "🐋",
      "manifest": "bundles/sea-creatures/bundle.json"
    }
  ]
}
```

Each published bundle in `bundles/<name>/` contains only its metadata manifest and final vector SVG pages:

```text
bundles/<name>/
├── bundle.json
└── pages/
    ├── 01.svg
    └── ...
```

`bundle.json` schema:

```json
{
  "id": "sea-creatures",
  "name": "Sea Creatures",
  "icon": "🐋",
  "description": "Concise search-friendly summary of the bundle.",
  "prompt": "Originating bundle prompt or brief.",
  "pages": [
    {
      "id": "01",
      "title": "Blue whale",
      "image": "pages/01.svg",
      "description": "Concise search-friendly description of the page scene."
    }
  ]
}
```

Page `image` paths are relative to `bundle.json`. Do not commit intermediate generation, review, raster, or print-proofing artifacts into `bundles/<name>/`.

## Generated-bundle prototype

The local-only `coloring-bundle` skill (`.agents/skills/coloring-bundle`, excluded from Git via `.git/info/exclude`)
lets a Pi agent generate and review a coloring collection, then trace A4 SVGs and a vector PDF for local proofing. In Pi, run `/reload`, then for example:

```text
/skill:coloring-bundle Four friendly woodland animal pages for ages 5–7
```

The skill pauses for human approval and uses Pi's image models rather than a
separate generation service. Working artifacts (brief, notes, prompts, originals,
review sheets, and proofing exports) stay in the gitignored `work/<name>/` folder.
After approval, only the final vector SVGs (`pages/*.svg`) and `bundle.json` are
written to `bundles/<name>/`, registered in `catalog.json`, and published by a pull
request. The skill does not touch git. See the skill README for dependency setup
and the export command.
