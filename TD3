# README for TD-3: Spatial SQL Functions

## Overview
This practical assignment explores the use of spatial SQL functions in PostGIS to analyze geospatial data. The focus is on determining the parcels located within a specified distance from fire points and visualizing the data using QGIS.

## Key Tasks

### 1. Import Shapefiles into PostGIS
- Download the shapefile containing parcel data.
- Use the **PostGIS Shapefile Import/Export Manager** to load the shapefile into a PostgreSQL table.
  - Select the shapefile and specify the target table.
  - Import the data successfully into the database.

### 2. Query Parcels Data
- Execute the following SQL query in pgAdmin to count the number of parcels:
  ```sql
  SELECT COUNT(*) FROM parcels;
  ```
- View the first few rows of the data to verify:
  ```sql
  SELECT * FROM parcels LIMIT 5;
  ```

### 3. Identify Fire Points
- Determine the centroid of a specific parcel to represent the fire point. Use the following SQL query:
  ```sql
  SELECT ST_Centroid(geom) AS fire_point
  FROM parcels
  WHERE gid = 462273;
  ```

### 4. Analyze Risk Zones
- Use QGIS to duplicate the `parcels` layer and name it `fire-risk`.
- Apply a filter to select parcels within a 1 km radius of the fire point using the following expression:
  ```sql
  ST_DWithin(geom, (SELECT ST_Centroid(geom) FROM parcels WHERE gid = 462273), 1000)
  ```
- Update the symbology of the layer to visualize risk zones.
- Identify an additional fire point (e.g., parcel `gid = 460957`) and update the filter to include both locations.

### 5. Advanced Queries
- Use pgAdmin or QGIS to execute the following advanced spatial queries:
  - **Count parcels within 1 km of both fire points**:
    ```sql
    SELECT COUNT(*)
    FROM parcels
    WHERE ST_DWithin(geom, (SELECT ST_Centroid(geom) FROM parcels WHERE gid = 462273), 1000)
       OR ST_DWithin(geom, (SELECT ST_Centroid(geom) FROM parcels WHERE gid = 460957), 1000);
    ```
  - **Calculate the total area of parcels near fire points**:
    ```sql
    SELECT SUM(ST_Area(geom))
    FROM parcels
    WHERE ST_DWithin(geom, (SELECT ST_Centroid(geom) FROM parcels WHERE gid = 462273), 1000)
       OR ST_DWithin(geom, (SELECT ST_Centroid(geom) FROM parcels WHERE gid = 460957), 1000);
    ```

## Learning Objectives
- Gain proficiency in using spatial SQL functions for geospatial analysis.
- Integrate QGIS and PostGIS to visualize and filter spatial data.
- Perform advanced geospatial queries to analyze and interpret data.

## Additional Resources
- Official [PostGIS Documentation](https://postgis.net/documentation/).
- QGIS [User Guide](https://docs.qgis.org/).
- PostgreSQL [Documentation](https://www.postgresql.org/docs/).
