# How Did It Snow in Texas? Houston Blackouts from the February 2021 Winter Storms

## About

This repository contains Homework 4 for EDS 223 (Geospatial Analysis & Remote Sensing) in the UCSB Master of Environmental Data Science program. It estimates how many homes in the Houston metropolitan area lost power during the February 2021 Texas winter storms, using satellite night lights data:

- Merges VIIRS night lights tiles for 2021-02-07 (before the storms) and 2021-02-16 (after).
- Builds a blackout mask from cells where night light intensity dropped by more than 200 nW cm<sup>-2</sup> sr<sup>-1</sup>, then crops it to Houston.
- Removes areas within 200 m of highways, where light changes may not be caused by the storm.
- Counts the OpenStreetMap homes that fall inside the blackout areas.

## Repository Structure

```
eds223-hw4-how-did-it-snow-in-texas
├── README.md
├── .gitignore
├── texas_blackout.qmd     # Quarto document with analysis
└── data/                  # Not tracked (see Data Access)
    ├── gis_osm_buildings_a_free_1.gpkg
    ├── gis_osm_roads_free_1.gpkg
    ├── ACS_2019_5YR_TRACT_48_TEXAS.gdb
    └── VNP46A1/
        ├── VNP46A1.A2021038.h08v05.001.2021039064328.tif   # 2021-02-07
        ├── VNP46A1.A2021038.h08v06.001.2021039064329.tif   # 2021-02-07
        ├── VNP46A1.A2021047.h08v05.001.2021048091106.tif   # 2021-02-16
        └── VNP46A1.A2021047.h08v06.001.2021048091105.tif   # 2021-02-16
```

## Data Access

The data is **not stored in this repository** because `data/` is listed in `.gitignore`. The prepared data was provided through the EDS 223 course. To run the analysis, place it in `data/` following the structure shown above. It includes:

- **Night lights:** VIIRS VNP46A1 tiles h08v05 and h08v06 from NASA's LAADS DAAC.
- **Roads and homes:** OpenStreetMap highways and buildings for the Houston area, downloaded from Geofabrik.
- **Census data:** 2019 American Community Survey (5-year) tract data for Texas.

## Author

Calvin Fu ([@cuvlin](https://github.com/cuvlin))

## References

- NASA LAADS DAAC. *VIIRS/NPP Daily Gridded Day Night Band 500m Linear Lat Lon Grid Night (VNP46A1)* [Data set]. https://ladsweb.modaps.eosdis.nasa.gov/
- OpenStreetMap contributors. *OpenStreetMap data for Texas*, via Geofabrik [Data set]. https://download.geofabrik.de/
- U.S. Census Bureau. *American Community Survey 2019 5-Year Estimates* [Data set].
- Wikipedia. (2021). *2021 Texas power crisis*. https://en.wikipedia.org/wiki/2021_Texas_power_crisis
- EDS 223 Class Page (found [here](https://eds-223-geospatial.github.io/))

## Acknowledgements

This assignment was completed as part of EDS 223 at the Bren School of Environmental Science & Management, UC Santa Barbara.
