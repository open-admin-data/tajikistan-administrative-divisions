# Tajikistan Administrative Divisions / Тоҷикистон



## Overview

| Item | Details |
|------|---------|
| Province | 5 |
| District | 76 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/tj](https://openadmindata.org/tj/) |
| API | [openadmindata.org/api/tj](https://openadmindata.org/api/tj/) |
| Flag | [PNG](https://onlygames.me/flags-png/tj/) · [SVG](https://onlygames.me/flags-svg/tj/) · [PDF](https://onlygames.me/flags-pdf/tj/) |
| National Anthem | [🎵 Listen & Download Tajikistan National Anthem MP3](https://onlygames.me/national-anthems/tj/) |

## Browse by Province

| # | Province | Districts | Link |
|---|----|----|------|
| 1 | Душанбе (Dushanbe) | 4 | [Browse](divisions/dushanbe-tjk001/) |
| 2 | Суғд (Sughd) | 22 | [Browse](divisions/sughd-tjk002/) |
| 3 | Хатлон (Khatlon) | 27 | [Browse](divisions/khatlon-tjk003/) |
| 4 | Ноҳияҳои тобеи ҷумҳурӣ (Districts of Republican Subordination) | 15 | [Browse](divisions/districts-of-republican-subordination-tjk004/) |
| 5 | Мухтори Кӯҳистони Бадахшон (Gorno-Badakhshan) | 8 | [Browse](divisions/gorno-badakhshan-tjk005/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 5 province records |
| [all-district.json](data/all-district.json) | JSON | All 76 district records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-province.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-province.json", "utf-8"));
console.log(`Total: ${data.length} provinces`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=province, 2=district |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{province-slug}/
```

Districts are listed inline in each province's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province links
- [Per-province data](docs/llms-full/) — Full data by province

## Citation

```
Tajikistan Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/tajikistan-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
