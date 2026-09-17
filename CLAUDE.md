# FreeScout core app (Rubious/support)

This is the FreeScout core application for Fellowship's internal support desk, bind-mounted into the `freescout-app` container as `/www/html` (see `../docker-compose.yml` and `../CLAUDE.md` one level up for the wider project layout).

This repo (`Rubious/support`, branch `dist`) was reset from this local directory's live state on 17/09/2026 — the prior GitHub history was stale and out of date with what's actually running, so it was replaced rather than merged.

## Modules are separate repos

`Modules/<ModuleName>` (e.g. `LinkForecastTask`) is excluded here via `.gitignore` (`/Modules`) — each module is its own standalone git repo with its own GitHub remote. See `../CLAUDE.md` for the module deploy process.

## Live deployment

The live site (`ssh freescout`) runs this same core app, but its `data/` directory is **not** git-tracked — it's a plain deployed copy, not pulled from this repo. Don't assume pushing here updates the live site; core app changes are deployed by other means (docker image / manual copy), only modules are deployed via `git pull` on the live box.
