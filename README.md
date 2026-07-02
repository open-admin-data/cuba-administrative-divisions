# Cuba Administrative Divisions / Cuba



## Overview

| Item | Details |
|------|---------|
| Province | 16 |
| Municipality | 168 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-07-02 |
| Website | [openadmindata.org/cu](https://openadmindata.org/cu/) |
| API | [openadmindata.org/api/cu](https://openadmindata.org/api/cu/) |

## Browse by Province

| # | Province | Municipalitys | Link |
|---|----|----|------|
| 1 | Artemisa | 11 | [Browse](divisions/artemisa-cu01/) |
| 2 | Camagüey (Camaguey) | 13 | [Browse](divisions/camaguey-cu02/) |
| 3 | Ciego de Ávila (Ciego de Avila) | 10 | [Browse](divisions/ciego-de-avila-cu03/) |
| 4 | Cienfuegos | 8 | [Browse](divisions/cienfuegos-cu04/) |
| 5 | Granma | 13 | [Browse](divisions/granma-cu05/) |
| 6 | Guantánamo (Guantanamo) | 10 | [Browse](divisions/guantanamo-cu06/) |
| 7 | Holguín (Holguin) | 14 | [Browse](divisions/holguin-cu07/) |
| 8 | Isla de la Juventud | 1 | [Browse](divisions/isla-de-la-juventud-cu08/) |
| 9 | La Habana | 15 | [Browse](divisions/la-habana-cu09/) |
| 10 | Las Tunas | 8 | [Browse](divisions/las-tunas-cu10/) |
| 11 | Matanzas | 13 | [Browse](divisions/matanzas-cu11/) |
| 12 | Mayabeque | 11 | [Browse](divisions/mayabeque-cu12/) |
| 13 | Pinar del Río (Pinar del Rio) | 11 | [Browse](divisions/pinar-del-rio-cu13/) |
| 14 | Sancti Spíritus (Sancti Spiritus) | 8 | [Browse](divisions/sancti-spiritus-cu14/) |
| 15 | Santiago de Cuba | 9 | [Browse](divisions/santiago-de-cuba-cu15/) |
| 16 | Villa Clara | 13 | [Browse](divisions/villa-clara-cu16/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 16 province records |
| [all-municipality.json](data/all-municipality.json) | JSON | All 168 municipality records |
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
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['municipality']} municipalitys")
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
| `level` | integer | 1=province, 2=municipality |
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

Municipalitys are listed inline in each province's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province links
- [Per-province data](docs/llms-full/) — Full data by province

## Citation

```
Cuba Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/cuba-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
