# Data Notes

## Ibadan North-East LGA boundary, extracted via QuickOSM
- Source: Query: admin_level = 6 within Ibadan North-East extent
- Extracted: 07/09/2026
- 1 feature, polygon
- Columns: full_id (text), osm_id (text), osm_type (text), admin_leve (text), old_name (text), name_en (text), alt_name (text), species_wi (text), species__1 (text), source_dat (text), name_zh (text), name_yo (text), wikipedia (text), wikidata (text), name_ru (text), official_n (text), name_ar (text), type (text), official_1 (text), name_fr (text), name (text), boundary (text)
- There are nulls in old_name, name_en, alt_name, species_wi, species__1, name_zh, name_yo, name_ru, official_n, name_ar, official_1, name_fr
- Covers the full extent of Ibadan North-East LGA
- Attribution: © OpenStreetMap contributors
- Use License: Open Database Licence version 1.0 (the ODbL)

## Ibadan North-East LGA Building footprints, extracted via QuickOSM
- Source: Query: building =* within Ibadan North-East extent
- Extracted: 07/09/2026
- 34028 features, polygons
- Columns: full_id (text), osm_id (text), osm_type (text), building (text), roof_shape (text), house (text), height (text), ele (text), building_l (text), building_c (text), fuel_petro (text), fuel_diese (text), opening_ho (text), wikidata (text), sport (text), descriptio (text), tourism (text), rooms (text), guest_hous (text), addr_stree (text), addr_house (text), addr_city (text), smoking (text), religion (text), denominati (text), office (text), government (text), osm_id_2 (text), fclass (text), code (text), layer (text), building_1 (text), amenity (text), name (text), level (text), type (text)
- All fields contain null, except full_id, osm_id, osm_type, building and type
- It covers the full extent of Ibadan North-East LGA
- Attribution: © OpenStreetMap contributors
- Use License: Open Database Licence version 1.0 (the ODbL)

## Settlement Extents v4.1 - GRID3 
- Source: https://data.grid3.org/datasets/GRID3::grid3-nga-settlement-extents-v4-1/
- Downloaded: 07/09/2026
- 820 features, polygons
- Columns: fid (double), block_id (text), country (text), iso3 (text), block_area (double), block_peri (double), block_neig (double), building_c (integer), building_a (double), building_1 (double), building_2 (double), building_3 (double), building_4 (double), building_5 (double), extent_typ (text), mgrs_code (text), ndvi_mean (double), evi_mean (double), gbuilding_ (double), gbuildin_1 (double), blocks_per (double), building_6 (double), building_m (double), building_7 (double), bd_class (text), ma_class (text), composite_ (text
- No field contains null
- I feel it covers the full extent of Ibadan North-East LGA
- Attriution: Center for Integrated Earth System Information (CIESIN), Columbia University. 2026. GRID3 NGA - Settlement Extents v4.1. New York: Columbia University. https://doi.org/10.7916/73v5-mq06. Accessed 07-09-2026
- Use License: CC BY-SA 4.0 License

## Watercourses in Ibadan North-East LGA, extracted via QuickOSM
- Source: Query: waterway =* within Ibadan North-East extent
- Extracted: 07/09/2026
- 39 features, lines
- Columns: full_id (text), osm_id (text), osm_type (text), waterway (text), tunnel (text), layer (text), level (text), name (text), boat (text)
- Some fields do not have null, but some have showing that that information is not known for that property
- I feel it covers the full extent of Ibadan North-East LGA, overlaying it on the downloaded DEM data
- Attribution: © OpenStreetMap contributors
- Use License: Open Database Licence version 1.0 (the ODbL)

## Elevation data - Copernicus DEM GLO-30 
- Source: https://portal.opentopography.org/raster?opentopoID=OTSDEM.032021.4326.3
- Downloaded: 08/09/2026
- Raster
- After clipping the raw DEM to the extent of the Ibadan North-East LGA, assigning a value of 999999 to the NoData box, the output shows areas (around the edges) that are not covered by the clipped DEM
- Attribution: European Space Agency (2024).  <i>Copernicus Global Digital Elevation Model</i>.  Distributed by OpenTopography.  https://doi.org/10.5069/G9028PQB. Accessed 2026-10-03
- Use License: © DLR e.V. 2010-2014 and © Airbus Defence and Space GmbH 2014-2018 provided under COPERNICUS by the European Union and ESA; all rights reserved

## CRS and Preparation
- All source layers were in EPSG: 4326 when downloaded
- Study area: Ibadan North-East, extracted from OpenStreetMap via QuickOSM in QGIS
- All layers (settlement extents, buildings, roads and DEM) have been clipped to the study area, then reprojected to EPSG: 32631 (UTM 31N)
- Area check: Ibadan North-East is 13km2. It does not match published figure because the shapefile chosen differs from the widely acclaimed shape (similar to the one on GRID3). The reason for sticking to this one from QuickOSM is because it tallies with data from the governmental bodies like the Ibadan Urban Flood Management Project and the Ministry of Lands, Physical Planning and Urban Development.
- Working files in data/processed, raw files untouched

## Quality Checks

### Settlement Extents v4.1
- Completeness: There are no gaps in the settlement data. It covers the whole extent of the study area.
- Currency: The version v4.1 is well appropriate for this project as it was published July 27, 2026 and last updated on September 11, 2026.
- Positional accuracy: The data aligns well with satellite imagery and has no visible offset.
- Attribute accuracy: Some of the attributes tally with the satellite imagery (like the block neighbour), but some do not. The ones that do not have no potential effect (like the building count in each settlement) as they can be sourced from other data.
- Fitness for purpose: The data is adequate for the analysis required.

### Ibadan North-East LGA Building footprints
- Completeness: There are no gaps in the settlement data. It covers the whole extent of the study area.
- Currency: The data when compared with satellite imagery is up to date as all buildings were captured.
- Positional accuracy: The data aligns well with satellite imagery and has no visible offset.
- Attribute accuracy: The available data attributes are adequate for the analysis.
- Fitness for purpose: The data is adequate for the analysis required.

### Watercourses in Ibadan North-East LGA
- Completeness: The data covers all visible watercourses when overlayed on satellite imagery.
- Currency: The data when compared with satellite imagery is up to date.
- Positional accuracy: The data aligns well with satellite imagery and has no visible offset.
- Attribute accuracy: The available data attributes are adequate for the analysis. However, some names are missing (all streams). This is not expected to affect the analysis as they drain into the other ones (rivers).
- Fitness for purpose: The data is adequate for the analysis required.

### Elevation data - Copernicus DEM GLO-30 
- Completeness: The data covers all visible watercourses when overlayed on satellite imagery.
- Currency: The DEM data is the most recent one available on the platform, last updated in 2024.
- Positional accuracy: The data aligns well with the watercourse feature and has no visible offset.
- Attribute accuracy: The available data attributes are adequate for the analysis.
- Fitness for purpose: The data is adequate for the slope analysis required.
