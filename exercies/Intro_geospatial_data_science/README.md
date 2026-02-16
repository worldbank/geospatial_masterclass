# Introduction to Geospatial Data Science
## Projections and Coordinate Systems

The notebook __exploring_projections.ipynb__ will walk you through opening a vector dataset and plotting it in different projections. If you are looking for a challenge, you can start from scratch to answer these three questions:

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