# KML-Clustering-Analysis

## Overview  
This repository contains a Python notebook that extracts geographic coordinates from a KML file and performs spatial clustering using the DBSCAN algorithm. The analysis helps identify clusters of locations based on proximity and density, useful for geospatial insights and mapping.

---

## Workflow and Logic  

### 🔹 Step 1: Extract Coordinates  
**Objective**: Parse a KML file and extract latitude and longitude values for each geographic point.

**Process**:
- Parsed the KML using `ElementTree`.
- Extracted coordinates nested within `<Placemark>` tags.
- Converted the long-lat string into a structured format using Python.

---

### 🔹 Step 2: Cluster with DBSCAN  
**Objective**: Group nearby coordinates into clusters using a density-based algorithm.

**Libraries Involved**:  
`numpy`, `scikit-learn`

**Process**:
- Converted coordinates to radians for Haversine distance.
- Applied `DBSCAN` with parameters `eps` and `min_samples`.
- Generated cluster labels for each coordinate point.

---

### 🔹 Step 3: Visualize Clusters  
**Objective**: Display the clustering results using both static and interactive maps.

**Tools Used**:  
- `matplotlib`: For static scatter plots.  
- `folium`: For an interactive map with color-coded clusters.

**Details**:
- Each cluster is shown with a distinct color.
- Noise points (unclustered) are marked in gray.
- Interactive map includes marker popups for location coordinates.

---

## Notes  

- The DBSCAN algorithm uses geographic (Haversine) distance to detect clusters.
- Only basic KML structures are supported (standard `<Point>` tags). Complex nested formats may require additional parsing logic.
- The notebook is modular and allows parameter adjustments for `eps` (radius) and `min_samples` (cluster density).
