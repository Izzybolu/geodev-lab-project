# **Data preparation**

**Week 3 deliverable.** GeoDev Lab Africa, Cohort One.
Author: Israel ODETOLA

What I reprojected, what I clipped, what I checked, and what I fixed.

---

## 1. Coordinate system decisions

**Working CRS:** <EPSG:32631>

**Why this one:** This project deals with measurement of distances (buffer analysis) in metres. Also, the study area falls within UTM Zone 31N, hence this CRS.

| Dataset | CRS as downloaded | CRS after | Operation |
|---|---|---|---|
| Ibadan North-East LGA Boundary | EPSG:4326 | EPSG:32631 | Reprojected |
| Settlement Extents v4.1 | EPSG:4326 | EPSG:32631 | Reprojected |
| Watercourses | EPSG:4326 | EPSG:32631 | Reprojected |
| Copernicus DEM GLO-30 | EPSG:4326 | EPSG:32631 | Reprojected |

---

## 2. Clipping to the study area

### Settlement Extents v4.1
- **Boundary used:** Ibadan North-East LGA, QGIS
- **Features before clipping:** 2546560
- **Features after clipping:** 820

### Watercourses
- **Boundary used:** Ibadan North-East LGA, QGIS
- **Features before clipping:** 39
- **Features after clipping:** 39

`The features before and after are the same because the shapefile was downloaded straight from QGIS using QuickOSM.`

### Copernicus DEM GLO-30
- **Boundary used:** Ibadan North-East LGA, QGIS
- **Dimension before clipping:** 7376 x 7576 pixels
- **Dimension after clipping:** 162 x 211 pixels

`After clipping, some edges had missing pixels such that the raster does not fill all edges completely.`

---

## 3. The five quality checks

| Dataset | Completeness | Currency | Positional Accuracy | Attribute Accuracy | Fitness for Purpose |
|---|---|---|---|---|---|
|Settlement Extents v4.1|covers the whole extent of the study area|latest version (updatedon September 11, 2026)|aligns well with satellite imagery|most attributes tally with satellite imagery, but no potential effect from the rest|adequate for the analysis|
|Watercourses|covers all visible waterways when overlayed on satellite imagery|consistent with latest satellite imagery|aligns well with satellite imagery with no visible offset|most attributes tally with satellite imagery, but no potential effect from the rest|adequate for the analysis|
|Copernicus DEM GLO-30|covers the study area except tiny pixel-gaps at the edge|most recent data on the platform|aligns well with satellite imagery and follows watercourses|available data attributes are adequate for the analysis|adequate for the analysis|

---

## 4. Problems found, and what I did

The issue encountered is just the gaps that were not filled by the clipped DEM. Since these gaps are little and are only around the edge, I expect that they would not affect the slope analysis.

---

## 5. The analysis-ready outputs

- **Files:**
`data/processed/IB_NE_Buildings.gpkg`
`data/processed/IB_NE_Settlements.gpkg`
`data/processed/IB_NE_Waterways.gpkg`
`data/processed/IB_NE_DEM_Layer.gpkg`
- **Format:** GeoPackage
- **CRS:** <EPSG:32631>
- **Features:** 1
- **Produced by:** manually in QGIS

---

**Status:** Week 3 complete. First spatial analysis in Week 4.
