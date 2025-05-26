# Sentinel Data Query, Filtering, Visualization, and Excel Export using STAC API

This Jupyter Notebook provides a comprehensive workflow for accessing, filtering, visualizing, and exporting **Sentinel satellite imagery metadata** using the **STAC (SpatioTemporal Asset Catalog) API** from the **Copernicus Data Space Ecosystem**.

---

## Overview

The notebook demonstrates how to:

-  Connect to the **Copernicus STAC API** endpoint.
-  Define a geographic **Area of Interest (AOI)** using GeoJSON polygon coordinates.
-  Query **Sentinel satellite data** with constraints such as date range and cloud cover percentage.
-  Extract and filter metadata, including filtering by specific **tile IDs**.
-  Plot the distribution of tiles using **Seaborn & Matplotlib**.
-  Export the filtered metadata results to an **Excel file** with a dynamic filename.

> **Example use case**: The notebook filters **Sentinel-2 data** over **Laos** for **January to December 2022**, limiting scenes to **0%–30% cloud cover**.

---

## Prerequisites

Make sure the following Python libraries are installed:

```bash
pip install pandas pystac_client folium openpyxl matplotlib seaborn
```

For Jupyter or Google Colab, use:

```python
!pip install pandas pystac_client folium openpyxl matplotlib seaborn
```

---

## Notebook Structure

### 1️⃣ Import Libraries and Set Environment

- Loads essential libraries:
  - `pandas` for data handling
  - `pystac_client` for API interaction
  - `folium` for map visualization
  - `matplotlib` and `seaborn` for plotting

### 2️⃣ Connect to STAC API and Define AOI

- Connects to: [https://stac.dataspace.copernicus.eu/v1](https://stac.dataspace.copernicus.eu/v1)
- Defines **AOI** using GeoJSON (bounding box for Laos)

### 3️⃣ Visualize AOI with Folium

- Displays the AOI polygon on an interactive map for spatial context using `folium`

### 4️⃣ Query Sentinel Data

- Queries the **Sentinel-2 collection**
- Filters by:
  - Date range: `2022-01-01` to `2022-12-31`
  - Cloud cover: `0% to 30%`
- Retrieves metadata like tile ID, acquisition date, and cloud percentage

### 5️⃣ Metadata Extraction and Filtering

- Extracts metadata into a `pandas.DataFrame`
- Allows additional filtering by user-defined **tile IDs**

### 6️⃣ Visualization of Tile Distributions

- Visualizes:
  - Tile frequency distribution
  - Cloud cover statistics
- Uses `matplotlib` and `seaborn` for plotting

### 7️⃣ Export to Excel

- Exports the final filtered DataFrame to `.xlsx`
- Filename includes date range and timestamp (e.g., `Sentinel_Metadata_2022_Cloud0-30_<timestamp>.xlsx`)

---

## Usage Instructions

1. Open the notebook `sentinel_stac_filtering_visualization_export.ipynb`.
2. Install the required libraries if needed.
3. Run each cell in order to:
   - Query data
   - Apply filters
   - Visualize results
   - Export to Excel
4. Modify:
   - AOI polygon for a new region
   - Date range or cloud cover for different temporal/spatial filtering
5. Use the exported Excel for further analysis or reporting.

---

## Additional Information

- Utilizes **STAC API filtering capabilities**, including:
  - Cloud cover filtering
  - Tile ID selection
- Interactive mapping with **Folium**
- Export via **openpyxl** for Excel compatibility
- Flexible design for use with other **Sentinel missions** or **geographies**

---

## References

- [Copernicus Data Space Ecosystem STAC API](https://stac.dataspace.copernicus.eu/v1)
- [STAC Specification - Sentinel Hub Catalog API](https://docs.sentinel-hub.com/api/latest/api/catalog/)
- [pystac_client](https://pystac-client.readthedocs.io/)
- [Folium (Python mapping library)](https://python-visualization.github.io/folium/)
- [Pandas](https://pandas.pydata.org/)
- [Matplotlib](https://matplotlib.org/) and [Seaborn](https://seaborn.pydata.org/)

---

## Files

- `sentinel_stac_filtering_visualization_export.ipynb` - Main Notebook

---

## License

This notebook and its code are provided under the **MIT License**.
