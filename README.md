# 3D Scanning Community Keyword Star Map

Interactive keyword co-occurrence network from Reddit / YouTube 3D scanning communities.

Open the [live star map](https://yomuran.github.io/community-keywords-star/).

- **Click** a node to lock the side panel and browse all source links
- **Hover** for preview highlight only
- Data source: accumulated community keyword research (since 2025-07-01)

Regenerate locally from the parent repo:

```bash
cd community_keywords
python scripts/export_keyword_star_html.py
cp exports/keyword_star_map.html exports/gh-pages/index.html
```
