# Sero Official Loop Catalog

Curated, proven loops for the [Sero](https://sero.ai) Orchestrator — install
them from the **Catalog** tab in the Orchestrator library view, adapt them to
your workspace, review, and switch them on.

Entries in this repo are reviewed by the Sero team and show the **verified**
badge in the app. Anyone can run their own catalog: any git repo with this
layout works, added via *Add repo* in the Catalog tab. A private repo makes a
team catalog.

## Repo layout

```text
catalog.json                    # index: { "version": 1, "name": "…", "entries": ["<slug>", …] }
loops/<slug>/
  definition.json               # SharedLoopDefinition — the portable loop payload (schemaVersion 1)
  catalog.json                  # curated metadata (below)
  example-output.md             # optional, shown on the entry detail
```

## Entry metadata (`loops/<slug>/catalog.json`)

Required: `slug` (must match the directory name), `name`, `description`,
`version` (positive integer, bump it on every change to the entry).

Optional: `requiredTools` (tool names checked at install, missing ones warn),
`connectors` (human-readable needs, e.g. `"GitHub (gh login)"`),
`recommendedTrigger`, `delivery` (a Sero delivery destination id), `costBand`
(`low` | `medium` | `high`), `modelTier` (`LOW` | `MED` | `HIGH`),
`limitations` (honest caveats, shown on the card).

## Publishing an entry

Open a pull request against this repo:

1. Build and refine the loop in Sero, save it to your library, and export its
   definition.
2. Add `loops/<slug>/` with the definition, metadata, and (ideally) an
   example output.
3. Append the slug to `catalog.json`.

Keep prompts generic ("your repo", "your team channel") — the installer's
planner adapts each loop to the user's workspace. Entries may *require*
connectors; they must never install tools.

## Trust model

Installs never auto-activate: every install lands as a draft the user reviews
before it can run, external sends stay approval-gated, and loops run under the
user's normal agent permissions. This catalog adds no execution authority.
