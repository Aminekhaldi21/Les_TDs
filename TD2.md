# README for TD-2: Creating Tables with Spatial Columns

## Overview
This practical assignment focuses on creating and managing spatial tables in PostgreSQL using the PostGIS extension. It includes instructions for working with different geometry types (Point, Polygon, and Linestring) and integrating data with QGIS for visualization and editing.

## Key Tasks

### 1. Create a Point Table
- Use the following SQL command in pgAdmin to create a `points_of_interests` table:
  ```sql
  CREATE TABLE points_of_interests (
      id SERIAL PRIMARY KEY,
      nom VARCHAR(255),
      geom GEOMETRY(Point, 4326)
  );
  ```
- Connect to the database using QGIS by:
  - Right-clicking on PostgreSQL in the Explorer panel.
  - Adding a new connection with the required database details.
- Switch to editing mode in QGIS, add point data, and save the changes.
- Verify the data in pgAdmin with the following query:
  ```sql
  SELECT * FROM points_of_interests;
  ```

### 2. Create a Polygon Table
- Use the following SQL command to create a `zones_protegees` table:
  ```sql
  CREATE TABLE zones_protegees (
      id SERIAL PRIMARY KEY,
      nom VARCHAR(255),
      geom GEOMETRY(Polygon, 4326)
  );
  ```
- Populate the table with data using QGIS and save the changes.
- Verify the data in pgAdmin with the following query:
  ```sql
  SELECT * FROM zones_protegees;
  ```

### 3. Create a Linestring Table
- Repeat the process to create a table with a `Linestring` geometry column.

## Learning Objectives
- Practice creating spatial tables with different geometry types in PostgreSQL.
- Use QGIS to manage, visualize, and edit spatial data.
- Integrate PostgreSQL and QGIS for effective geospatial data handling.

## Additional Resources
- Official [PostGIS Documentation](https://postgis.net/documentation/).
- QGIS [User Guide](https://docs.qgis.org/).
- PostgreSQL [Documentation](https://www.postgresql.org/docs/).
