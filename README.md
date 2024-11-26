# US Counties and Locations with Albers Projection

This project visualizes US counties and IHEs using the Albers Equal Area projection. The map includes adjustments for Alaska, Hawaii, Puerto Rico, and Washington, D.C., ensuring all territories are accurately represented within the continental US map. The project also overlays college locations on the map.

## Features

- **County Shapefile Visualization:** Maps US counties using the Albers Equal Area projection.
- **College Locations Overlay:** Displays the location of IHEs in the same projection.
- **Territory Adjustments:** Adjusts Alaska, Hawaii, Puerto Rico, and Washington, D.C. for better visualization in Tableau.
- **State Boundary Aggregation:** Option to visualize US state boundaries instead of counties or for map overlay.

## Acknowledgements and Data Sources

- US county shapefile from Census Bureau
- IHEs lat and long from project-specific dataset

## Requirements

The project requires the following libraries:

- `pandas`
- `geopandas`
- `matplotlib`
- `shapely`
- `openpyxl` (for reading Excel files)

Install the required libraries with:

```bash
pip install pandas geopandas matplotlib shapely openpyxl
