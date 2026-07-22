# 3D Scanning Community Keyword Star Map

Interactive keyword co-occurrence network from Reddit / YouTube 3D scanning communities.

**Live site**: [yomuran.github.io/community-keywords-star](https://yomuran.github.io/community-keywords-star/)

## Features (v2)

- Semantic **cluster layout** — related keywords group together
- **Canonical** keywords with optional alias satellites
- Click a node to lock the side panel and scroll through all source links
- Header badge shows `lastFetchAt` from embedded network meta

## Regenerate & deploy

From the parent monorepo:

```bash
cd social_video_research/community_keywords

# Full weekly pipeline (= CI)
python scripts/weekly_refresh.py

# Export only (no API fetch)
python scripts/weekly_refresh.py --export-only
```

Artifacts written here:

- `index.html` — single-file interactive star map
- `keyword_network.json` — schema v2 network data
- `meta.json` — `lastFetchAt`, `rawCount`, `nodeCount`, `edgeCount`

## GitHub Pages deploy

This directory is a clone of `https://github.com/yomuran/community-keywords-star`.

`weekly_refresh.py` commits and pushes automatically when `GH_PAGES_DEPLOY_TOKEN` is set (CI). Manual push:

```bash
cd exports/gh-pages
git add index.html keyword_network.json meta.json
git commit -m "update star map v2"
git push origin main
```

### PAT setup (parent repo Secrets)

1. Create a fine-grained or classic PAT with **Contents: write** on `yomuran/community-keywords-star`
2. Add to parent repo **Settings → Secrets → Actions** as `GH_PAGES_DEPLOY_TOKEN`
3. Weekly workflow: `.github/workflows/community_keywords_weekly.yml`

Pages updates typically appear within ~5 minutes at the live URL.
