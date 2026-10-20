EO79 v36 Nationwide integration (PROVISIONAL)
1. Upload website files to GitHub Pages repo root.
2. Upload contents of your converter web_data folder under repo data/ preserving province directories:
   data/index.json
   data/abra/manifest.json
   data/abra/[all parts]
   ... etc.
3. This ZIP contains index.json but NOT the 79 provincial polygon datasets.
4. The old Abra v35 pilot files were removed. Do not upload old v35 data folder over new data.
5. Test data/index.json and province manifest/part URLs in browser.
6. The loader expects each province manifest to expose parts/chunks/files and each joined part stream to be gzip GeoJSON FeatureCollection.
7. Since actual converter v3 provincial manifest and chunks were NOT provided, this schema assumption must be checked using a sample before production.
8. Four failed provinces (Mountain Province, Pangasinan, Cavite, North Cotabato) have no usable provincial bbox in index. The website warns results are PROVISIONAL and cannot certify official nationwide completeness.
9. Bounding-box detection is a candidate filter, not exact provincial boundaries. Review cross-border parcels carefully.
10. v36 preserves v35 analysis and map exports; test with actual provincial data before use.
