<h1 align="center">US Counties and College Locations with Albers Projection</h1>
<h3 align="center">Mapping US Counties and Colleges with Adjusted Territories</h3>

## Background and Overview

This project visualizes US counties and overlays college locations using the Albers Equal Area projection. To maintain geographic accuracy while fitting all regions onto a single map, transformations are applied to Alaska, Hawaii, Puerto Rico, and Washington, D.C., adjusting their positions and scales relative to the continental US. The map also aggregates counties into state boundaries for high-level visualizations.

### Adjusted Territories and College Overlay

The following adjustments are made for accurate placement:
- `transform_alaska` Scaled down and shifted.
- `transform_hawaii` Enlarged and relocated.
- `transform_puerto_rico` Adjusted position and scale.
- `transform_dc` Enlarged and shifted for visibility.

Each function adjusts the geometry of respective regions to align with the map.

### Key Steps: `transform_alaska`
This function applies two transformations to Alaska's geometry:
```
def transform_alaska(geometry):
    # Translate and scale Alaska 
    return scale(translate(geometry, xoff=-2000000, yoff=-7000000), xfact=0.4, yfact=0.4, origin=(0, 0))

gdf.loc[gdf['STATEFP'] == '02', 'geometry'] = gdf.loc[gdf['STATEFP'] == '02', 'geometry'].apply(transform_alaska)
```
**1. Translation (`translate`)**:  
   Moves the geometry by a certain distance along the x-axis and y-axis. In this case:  
   - `xoff=-2000000`: Moves Alaska 2 million units to the left.  
   - `yoff=-7000000`: Moves Alaska 7 million units downward.

**2. Scaling (`scale`)**:  
   Shrinks the geometry by reducing its size by 40%.  
   - `xfact=0.4` and `yfact=0.4`: Scale factors for the x and y dimensions.  
   - `origin=(0, 0)`: The scaling is performed relative to the coordinate `(0, 0)`, ensuring consistency in how the geometry shrinks.

**3. Applying the Transformation**
   The code filters the GeoDataFrame (`gdf`) to select rows where `STATEFP` equals `'02'` (Alaska). For the selected rows, it applies the `transform_alaska` function to the `geometry` column, which contains Alaska's geometric shape.

**4. Updating the Geometry**
   The result of the `transform_alaska` function is saved back into the `geometry` column for Alaska.

## Maps:
1. **US Counties:**
   - County boundaries 
2. **US Counties with College Locations:**
    - County boundaries and college locations (blue markers).
2. **US State Boundaries:**
   - Aggregated state-level boundaries with adjusted territories.
  
## Dependencies

This project relies on the following Python libraries:
- `pandas`: Data manipulation.
- `geopandas`: Geospatial data processing.
- `matplotlib`: Visualization.
- `shapely`: Geometric transformations.
- `openpyxl`: For reading Excel files.

Install dependencies with:

```bash
pip install pandas geopandas matplotlib shapely openpyxl
```

## Authors
Sydney Leiher,
Data Scientist,
U.S. Department of Education

