# README for TD-1: Installation of PostGIS and Creation of a Spatial Database

## Overview
This practical assignment focuses on setting up a geospatial database environment using PostgreSQL and PostGIS. The goal is to install the necessary software, configure the environment, and create a spatial database to support geospatial data operations.

## Key Tasks

### 1. Download and Install PostgreSQL
- Visit the official [PostgreSQL download page](https://www.postgresql.org/download/) to get the latest version suitable for your operating system (Linux, MacOS, Windows).
- Follow the installation guide for your platform.
- During installation, set a password for the `postgres` user, which will be used later to connect to the database.

### 2. Download and Install PostGIS
- Ensure all components are selected during the PostgreSQL installation.
- Use the Stack Builder tool (launched at the end of PostgreSQL installation) to download and install PostGIS, the spatial database extension.
- Select the correct PostgreSQL version in the Stack Builder to ensure compatibility.

### 3. Create a Database Using pgAdmin 4
- Launch pgAdmin 4, the graphical management tool for PostgreSQL.
- Connect to the PostgreSQL server by entering the password set during installation.
- Expand the `Servers` node, right-click on `PostgreSQL`, and select **Create > Database**.
- Enter a name for the database (e.g., `spatial-db-1`) and click **Save**.

### 4. Add the PostGIS Extension
- In pgAdmin, select the newly created database.
- Open the Query Tool and execute the following SQL command:
  ```sql
  CREATE EXTENSION postgis;
  ```
- Execute the query by pressing **F5** or clicking the Execute button.
- Verify the installation by expanding the `Schemas` > `Public` > `Tables` section in pgAdmin. You should see a table named `spatial_ref_sys`, confirming the successful addition of the PostGIS extension.

## Learning Objectives
- Understand how to install and configure PostgreSQL and PostGIS.
- Learn how to set up a spatial database environment.
- Familiarize yourself with basic operations in pgAdmin for managing databases and extensions.

## Additional Resources
- Official [PostGIS Documentation](https://postgis.net/documentation/).
- PostgreSQL [Getting Started Guide](https://www.postgresql.org/docs/).
