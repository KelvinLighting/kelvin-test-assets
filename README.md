# kelvin-test-assets

Asset store for screenshots embedded in [KelvinLighting/Kelvin](https://github.com/KelvinLighting/Kelvin) issue and PR comments. The main Kelvin repo is private, so images must live somewhere GitHub's camo proxy can fetch anonymously — this deliberately blandly-named public repo is that place. Not a code repo; nothing here is part of the Kelvin product.

## Rules

1. **Filenames are immutable — never overwrite an existing file.** Issue comments embed raw URLs into this repo; overwriting or deleting a file breaks the rendered history of the issue that references it. A retake gets a new name (`-2` suffix).
2. **Uploads happen via `.claude/scripts/upload-issue-asset.sh` in the Kelvin repo** (GitHub contents API, one commit per image). No clones needed for day-to-day use.
3. Agents push to `main` directly — Kelvin's "no direct pushes to main" rule does **not** apply here; this repo is an append-only asset store with no CI and no review flow.
4. Soft cap ~5 MB per image. Palette-quantize large PNGs before uploading.

## Layout

- `issues/<n>/<short-name>.<ext>` — evidence for Kelvin issue/PR `#<n>`.
- `misc/<yyyy-mm-dd>-<short-name>.<ext>` — the rare image with no issue number.
- `legacy/` — one-time seed of the 108 images from the retired surge flow (`kelvin-issue-assets.surge.sh`, deployed from `knowledge/kelvin/issue-assets/`, frozen 2026-07-20). Old issue comments still point at surge; this folder is the durable backup if that site ever dies.

## URL shape

```
https://raw.githubusercontent.com/KelvinLighting/kelvin-test-assets/main/issues/<n>/<short-name>.png
```
