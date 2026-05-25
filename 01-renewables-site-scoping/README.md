[README_Renewables.md](https://github.com/user-attachments/files/28203383/README_Renewables.md)
# 01 — Renewables Site Scoping: Central Queensland Solar Farm Screening

## Project Overview

A preliminary greenfield screening exercise to identify suitable land parcels for solar farm development within a 10 km radius of a defined investigation point in Central Queensland. This project simulates an early-stage prospecting workflow using only publicly available data, as would be typical at the pre-feasibility stage of a renewable energy project.

---

## Objective

Identify one or more candidate cadastral parcels suitable for solar farm development, based on a combination of environmental constraint exclusions and a weighted multi-criteria suitability analysis.

---

## Data Sources

All datasets sourced from publicly available repositories, including:

- **Cadastral boundaries** — Queensland property parcel data
- **Protected areas** — Queensland protected area estate
- **Watercourses & water bodies** — Queensland hydrography datasets
- **Flood extent** — Queensland flood mapping data
- **Transmission lines & substations** — infrastructure network data
- **Road network** — Queensland road dataset (filtered to exclude walkways and bike paths)
- **QLUMP land use zoning** — Queensland Land Use Mapping Program
- **Digital Elevation Model (DEM)** — terrain data for slope and aspect derivation

---

## Methodology

### 1. Constraint Exclusions (Hard Filters)

Areas were excluded from consideration based on the following criteria:

| Layer | Buffer / Exclusion | Justification |
|---|---|---|
| Protected Areas | 500 m buffer | Conservative conservation buffer beyond legal boundary, accounting for potential impacts and ecological corridors |
| Major Watercourses | 100 m buffer | Consistent with DA riparian setback requirements for significant waterways |
| Water Bodies | 50 m buffer | Environmental setback from lake and reservoir margins for water quality protection |
| Transmission Lines | 100 m buffer | Standard powerline easement width plus conservative construction margin |
| Roads | 30 m buffer | Safety setback from road corridors for solar farm operations |
| Flood Extent | Direct exclusion | Floodplain areas represent unacceptable risk for large-scale infrastructure |
| QLUMP Zoning | Direct exclusion | Urban, industrial, water, irrigated agriculture, and conservation land uses excluded |

Cadastral parcels were also filtered to:
- **Private land only** — government-owned easements excluded
- **Minimum area ≥ 1,000,000 m²** (100 ha) — appropriate for at least mid-scale solar development

### 2. Weighted Suitability Analysis

Remaining parcels were scored against four criteria using a 0–3 classification scale:

**Slope**
| Score | Range |
|---|---|
| 3 — Highly Suitable | 0–3° |
| 2 — Suitable | 3–5° |
| 1 — Feasible | 5–10° |
| 0 — Not Viable | >10° |

**Aspect**
| Score | Azimuth |
|---|---|
| 3 — Highly Suitable | 315–45° (north-facing) |
| 2 — Suitable | 270–315° & 45–90° |
| 1 — Feasible | 90–135° & 225–270° |
| 0 — Not Viable | 135–225° (south-facing) |

**Proximity to Transmission Lines**
| Score | Distance |
|---|---|
| 3 — Highly Suitable | 0–2 km |
| 2 — Suitable | 2–5 km |
| 1 — Feasible | 5–10 km |
| 0 — Not Viable | >10 km |

**Proximity to Substations**
| Score | Distance |
|---|---|
| 3 — Highly Suitable | 0–2 km |
| 2 — Suitable | 2–5 km |
| 1 — Feasible | 5–10 km |
| 0 — Not Viable | >10 km |

**Criteria Weighting**

| Criteria | Weight | Justification |
|---|---|---|
| Proximity to Transmission Lines | 30% | Grid connection is the largest cost driver in solar farm development |
| Proximity to Substations | 25% | Substations are direct grid connection points; proximity reduces infrastructure requirements |
| Slope | 25% | Terrain slope directly impacts earthworks costs, panel efficiency, and stormwater management |
| Aspect | 20% | North-facing slopes maximise solar radiation capture in the Southern Hemisphere |

### 3. Candidate Selection & Digitising

A candidate polygon was digitised at the cadastral parcel level. The selected parcel was attributed with:
- Name
- Area (ha)
- Short rationale

---

## Results

### Primary Candidate

The primary candidate scored highly across all weighted suitability criteria — exhibiting low gradient, a northerly aspect, and strong proximity to major transmission lines and nearby substations. Minor watercourse influence was minimal, reducing exposure to flooding and erosion risk. The entire parcel was contained within the 10 km investigation radius, road access was appropriate for construction and ongoing maintenance, and the single-cadastre selection simplifies land acquisition. The parcel exceeded the 100 ha minimum area threshold.

### Backup Candidate

A backup candidate was also identified based on its high suitability score and similarly low surrounding gradient. However, it lacks direct road access to the parcel and shows greater minor watercourse influence compared to the primary candidate.

---

## Outputs

- 📄 `maps/` — Exported PDF map (constraint layers, suitability surface, candidate polygon, legend, north arrow, scale bar)
- 📄 `docs/` — Methodology and justification document

---

## Key Skills Demonstrated

- Public data sourcing and import into QGIS
- Buffer analysis and hard constraint exclusion
- DEM-derived terrain analysis (slope and aspect)
- Raster suitability scoring and weighted overlay
- Cadastral data filtering and parcel-level analysis
- Candidate polygon digitising with attributed data
- Professional map production (PDF export with cartographic elements)
