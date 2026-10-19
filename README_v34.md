# EO79 SAFDZ v34 – Abra built-in pilot

Deploy all contents of this folder to the GitHub Pages repository root, **including `data/abra.geojson.gz`**. Do not upload only the HTML.

Upload a mining parcel inside Abra. The page fetches compressed Abra SAFDZ automatically, selects bounding-box candidates, then runs the existing polygon clipping, area computation and map rendering.

The original Abra shapefile was reprojected from PRS92 / UTM 51N to WGS84; polygon coordinates were not simplified. Only SAFDZ class and provenance fields are retained. No NPAAAD layer is included.

Limitations: Abra only. Nationwide rollout requires separately preparing and hosting remaining provinces. Online hosting is required; opening index.html directly with file:// will not permit fetching the data. The login is client-side only and does not secure public data. Very large parcels may still take time to clip.
