# Digitizing Lobar: GIS Analysis of a 1:50,000 Topographic Map

**Location:** Lobar, Samburu County, Kenya — Toposheet 65/1
**Coordinate System:** Geographic Coordinate System, Arc 1960
**Tools:** Esri ArcMap 10.8
**Date:** May 2026

![Lobar Topographic Map](Lobar_Topo_Map_preview.png)

## Overview

This project digitizes a scanned 1:50,000 topographic map of Lobar in northern Kenya into vector GIS layers, then performs buffer analysis to assess infrastructure–environment conflicts in an arid pastoralist landscape.

Lobar sits in Samburu County — a region defined by seasonal rivers (luggas), scattered waterholes, and the pastoralist routes that connect them. Turning a paper map into usable spatial data meant making real decisions about which features matter most in this kind of landscape.

## What I Built

**12 feature classes digitized:**

- **Points:** Schools, Markets, Waterholes
- **Lines:** Rivers, Tracks, Foot Paths, Boundaries
- **Polygons:** Hills, Plateaus, Swamps, Valleys

**Buffer analysis performed:**

- 500 m buffer around tracks — to assess which schools would be affected by a policy requiring schools to sit at least 500 m from roads
- 300 m buffer around rivers — to assess which developments would be affected by a policy restricting development within 300 m of rivers

## Methodology

1. **Georeferenced** the scanned topographic sheet using four corner control points, with longitude and latitude read from the sheet margins.
2. **Clipped** the map face to remove marginal information.
3. **Created and digitized** vector shapefiles for each feature type, building attribute tables as I went.
4. **Symbolized** features using standard cartographic conventions — blue for water, brown for boundaries, green for hills and vegetation.
5. **Performed buffer analysis** with the Buffer tool to derive the 500 m and 300 m proximity zones.
6. **Composed the final map** with title, legend, scale bar, north arrow and neat line, then exported to PDF.

A full step-by-step walkthrough with screenshots is in `report/Final_Report.pdf`.

## Key Decisions

- **Waterholes were added as point features beyond the original brief.** In arid Lobar, waterholes are among the most significant features on the map — they shape settlement patterns and seasonal livestock movement. Leaving them out would have missed what the landscape is actually about.
- **Fragmented river segments were merged.** ArcMap's double-click sketch termination had split single rivers into multiple polylines. These were consolidated using the Editor's Merge tool so that one river corresponds to one attribute record where appropriate.

## Lessons Learned

- ArcMap's standard label engine suppresses overlapping labels by default; showing all feature names required the "place overlapping labels" option and, in places, the Maplex Label Engine.
- Schema changes such as adding a field cannot be done inside an active edit session — the session must be stopped first.
- Saving the map document frequently is essential; digitizing represents hours of work that is easy to lose.

## Repository Contents

| Path | Description |
|------|-------------|
| `Lobar_Topo_Map.pdf` | Final cartographic output |
| `Lobar_Topo_Map_preview.png` | Preview image of the final map |
| `report/Final_Report.pdf` | Methodology report with process screenshots |
| `shapefiles/` | All vector data created in the project |
| `screenshots/` | Stage-by-stage process documentation |

> **Note:** The original scanned topographic sheet and the georeferenced raster are not included here due to file size. The vector shapefiles, final map and report capture the full workflow and results.

## Coursework Context

Produced as the Term Paper for  GIS Principles & Analytics, Data Science, May 2026.

## Contact

Angela Ngatia
(https://www.linkedin.com/in/angela-ngatia-05b65a256/) angelangatia564@gmail.com
