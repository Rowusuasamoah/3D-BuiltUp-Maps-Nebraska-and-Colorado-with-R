# 3D-BuiltUp-Maps-Nebraska-and-Colorado-with-R
3D visualizations of built-up area in clorado and nebraska using R, rayshader, and GHSL data
This project visualizes built-up areas in **Colorado** and **Nebraska** using open geospatial data and the **rayshader** package in R.

## 🔧 Tools Used
- R (`tidyverse`, `terra`, `rayshader`, `sf`, `elevatr`, `png`)
- GHSL Built-Up Grid (2020)
- DEM elevation from elevatr
- HTML via R Markdown

## 📊 What's Inside
- `3D_Built_Up_Area_Map_Colorado_and_Nebraska.Rmd`: Full R Markdown code
- `3D_Built_Up_Area_Map_Colorado_and_Nebraska.html`: Viewable version
- Rendered PNGs of each map

## 📌 What This Shows
- Urban development over topography
- Terrain constraints on settlement
- Aesthetic 3D mapping with rayshader
---
📍Built by Raymond Asamoah| #RStats #GIS #RemoteSensing
# 3D Built-Up Area Maps Using R

## 🧩 Sample Code

```r
# Load state boundary
us_states <- ne_states(country = "United States of America", returnclass = "sf")
colorado_sf <- us_states %>% filter(name == "Colorado")

# Get elevation
elev_co <- get_elev_raster(locations = colorado_sf, z = 8, clip = "locations")

# Crop built-up layer
ghs_raster <- rast("GHS_BUILT_S_NRES_E2020_GLOBE_R2023A_4326_3ss_V1_0.tif")
colorado_builtup <- crop(ghs_raster, vect(colorado_sf), snap = "in", mask = TRUE)

OUTPUT
FULL CODE
See the full RMarkdown file for step by step processing and rendering.
