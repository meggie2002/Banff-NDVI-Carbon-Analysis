# Banff National Park: Estimating Tree Cover and Carbon Stock from Satellite Imagery

## Overview

This project analyzes Sentinel-2 satellite imagery to estimate vegetated area, carbon stock, and carbon credits for a forested region in Banff National Park, Alberta, Canada. Using NDVI, we map healthy vegetation and calculate the region's carbon sequestration potential.

## Objectives

- Detect and map vegetated areas using NDVI.
- Estimate total vegetated area (hectares).
- Calculate total carbon stock (tonnes of carbon).
- Estimate CO₂ sequestration and potential carbon credits.

## Data Sources

- **Satellite Data:** Sentinel-2 L2A (Surface Reflectance)
- **Bands Used:** B04 (Red), B08 (Near Infrared)
- **Image Date:** June 29, 2025 (cloud-free)
- **Download Platform:** [Sentinel Hub EO Browser](https://apps.sentinel-hub.com/eo-browser)

## Methods

### NDVI Calculation

NDVI = (NIR - Red) / (NIR + Red)

- NDVI > 0.3 is considered healthy vegetation.

### Vegetation Mapping

- Pixels with NDVI > 0.3 are classified as vegetated.
- Vegetated area is calculated by counting these pixels and converting to hectares.

### Carbon Stock Estimation

- **Assumed Carbon Density:** 50 tonnes of carbon per hectare (standard for dense forests).
- **Total Carbon Stock:** Vegetated area (ha) × carbon density.
- **CO₂ Equivalent:** Total carbon × 3.67 (molecular conversion factor).
- **Carbon Credits:** 1 credit = 1 tonne CO₂ sequestered.

## Results

| Metric                  | Value                  |
|-------------------------|------------------------|
| Vegetated Area          | 7,987.15 hectares     |
| Carbon Stock            | 399,357.50 tonnes C   |
| CO₂ Sequestered         | 1,465,642.02 tonnes   |
| Potential Carbon Credits| 1,465,642 credits     |

## How to Run

### Requirements

Install dependencies using:
  pip install -r requirements.txt

### Steps

1. Download B04 (Red) and B08 (NIR) .tif files from Sentinel Hub EO Browser for the chosen date and region.
2. Place the `.tif` files in your working directory.
3. Run the provided Jupyter notebook (`analysis ndvi.ipynb`).



## References

- Sentinel Hub EO Browser: https://apps.sentinel-hub.com/eo-browser
- NDVI and Carbon Stock estimation methods 

## Notes

- The carbon stock estimate uses a standard value for dense forests; actual values may vary based on species and forest age.
- For large files (e.g., `.tif`), consider using `.gitignore` to avoid uploading unnecessary data to GitHub.


