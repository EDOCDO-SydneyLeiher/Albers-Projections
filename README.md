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


Maps include:
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

