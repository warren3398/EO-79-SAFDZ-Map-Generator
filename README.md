# EO 79 No-Go Zone for Mining – SAFDZ Map Generator

A browser-based GIS prototype based on the sample BSWM SAFDZ map layout and uploaded `SAFSZ STYLE.qml`.

## What it does
- Upload mining applicant parcel map as KML, zipped shapefile, or GeoJSON.
- Auto-clean / attempt geometry repair in-browser.
- Upload one or many SAFDZ province files at the same time as zipped shapefiles or GeoJSON. Multiple province layers are merged automatically before clipping, so a parcel crossing provincial boundaries is processed as one job.
- Auto-detect the SAFDZ classification field, clip SAFDZ polygons to the applicant parcel, and calculate hectares and percent of parcel.
- Uses satellite imagery with World Hillshade by default.
- Uses the official-style right-side BSWM layout, SAFDZ/non-SAFDZ legend, north arrow, scale, and editable map title/location text.
- Exports the map layout to JPEG or A4 landscape PDF.

## Color values loaded from the supplied QML
The QML explicitly contained these categories/colors:
- 1: RGB 59,230,127 (#3BE67F)
- 2: RGB 123,57,7 (#7B3907)
- 8: RGB 246,241,97 (#F6F161)
- 9: RGB 251,186,83 (#FBBA53)
- 10: RGB 162,164,163 (#A2A4A3)
- BU: RGB 185,185,185 (#B9B9B9)
- WB: RGB 87,249,255 (#57F9FF)

Classes 3–7 and Others are preloaded to visually match the supplied sample legend and remain editable in the website.

## Run
Open `index.html` in a modern browser with internet access. Internet is currently required for JavaScript libraries and the background satellite/hillshade services.

For best results, use a zipped shapefile containing `.shp`, `.shx`, `.dbf`, and `.prj` together. Very large nationwide shapefiles may be slow in a browser; a production deployment should use a spatial backend such as PostGIS/GeoServer for nationwide SAFDZ processing.

## Cross-province workflow
1. Upload the applicant parcel (KML, zipped shapefile, or GeoJSON).
2. In the SAFDZ uploader, select all affected province files at the same time (Ctrl/Shift selection where applicable).
3. The app cleans each layer, combines all SAFDZ features, retains the original source filename in `__source`, clips the combined layer to the parcel, and computes one combined hectare/percentage table.

## v10 background vector support
Background upload now supports GeoTIFF (.tif/.tiff), zipped Shapefile (.zip), GeoPackage (.gpkg), GeoJSON/JSON, and KML. Raster and vector backgrounds can be mixed in one upload. Vector layers are CRS-normalized to WGS84 where required and drawn behind SAFDZ and parcel layers. GeoPackage feature tables are loaded automatically.

- v13 portrait layout fix: A4 portrait now keeps map, title/conventional signs, legend, totals, and parcel area inside one page without clipping.


## v17
Replaced the website header with the supplied BSWM/ALMED EO 79 SAFDZ Map Generator banner.


## v23
Replaced graphic banner with a compact text-based DA-BSWM-ALMED institutional header and agency logos.


## v28 final polish
- Header title completed to “Executive Order No. 79 s. 2012 – No-Go Zone for Mining”.
- Geographic grid made more visible with darker blue, thicker stroke, higher opacity, and dashed line pattern.


## v29 layout fix
Landscape map layout compacted so the complete SAFDZ legend and parcel-area footer remain inside the page and exported JPEG/PDF.


## v31
Legend class rows use equal heights; the Description column is widened while Mapping Symbol, Ha and % are narrower. Official v30 SAFDZ colors and v29 bottom-fit behavior are retained.
