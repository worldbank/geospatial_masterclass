# Introduction to Geospatial Data Science
## Projections and Coordinate Systems
The notebook __exploring_projections.ipynb__ will walk you through opening a vector dataset and plotting it in different projections. If you are looking for a challenge, you can start from scratch to answer these questions:

1. Open the vector dataset on the new, official, World Bank Group boundaries  
  a. DDH link - https://datacatalog.worldbank.org/search/dataset/0038272/World-Bank-Official-Boundaries  
  b. ESRI rest endpoint - https://services.arcgis.com/iQ1dY19aHwbSDYIF/arcgis/rest/services/World_Bank_Global_Administrative_Divisions/FeatureServer/2 
2. Filter boundaries for a country of your choice  
3. Plot the vector boundaries 3-ways:  
  a. Simple plot of the unified geometry  
  b. Using geopandas.plot()  
  c. Using geopandas.explore()  
4. Explore how different projections affect maps: reproject your country into 3 different projections  
  a. Explore epsg.io or spatialreference.org (note that using 'ESRI:54009' is a good option for getting dramatic results)  
  b. Use geopandas.plot and matplotlib to plot all three side-by-each  
5. Filter countries again for Ghana (ISO_A3 = GHA) and calculate the area of the vector shapes using three projections:  
  a. EPSG codes: 2136, 32630, 'ESRI:54009'  
  b. Why does EPSG:2136 have such different results for the area calculation?

## Spatial Relationships and Raster extraction
The notebook __spatial_relationships.ipynb__ walks through some basic spatial relationships to identify intersecting shapes, and then uses those geometries to extract and aggregate raster data. If you are looking for a challenge, you can start from scratch to answer these three questions:

1. Open the adm1 and adm2 vector datasets of the official World Bank boundaries for your country of interest  
  a. See the first notebook on __exploring_projections.ipynb__ for links and semantics on this query
2. Select a single ADM1 by querying its primary key. Using that ADM1, identify the ADM2s using spatial relationships:  
  a. Intersect  
  b. Within  
  c. Plot a 3 panel image of the select ADM1, intersecting ADM2, and within ADM2
3. Read in a global landcover dataset from DDH:  
  a. [DDH link](https://datacatalogfiles.worldbank.org/ddh-published/0066950/DR0095711/ESACCI-LC-L4-LCCS-Map-300m-P1Y-2015-v2.0.7.tif)  
  b. Metadata: https://www.esa-landcover-cci.org/?q=node/175
4. Clip the raster to the select ADM1  
  a. See the [GOSTrocks.rasterMisc](https://github.com/worldbank/GOSTrocks/blob/main/src/GOSTrocks/rasterMisc.py) library for tips.  
  b. Compare clipping exactly to the ADM1 geography and to the ADM1 bounding box  
5. Using the rasterstats package (or the GOSTrocks.rMisc.zonalStats function) summarize unique landcover values in each ADM2.  
  a. Plot 3 different landcover classes as percentage coverage, including proper landcover labels