# Other Visualization: Geospatial Charts with Folium and GeoPandas

## 1. Introduction and definition
Geospatial visualization connects observations to geographic coordinates, boundaries or spatial relationships.

## 2. Why we need this
Maps are valuable when location is part of the question, but require correct coordinate reference systems and geographic context.

## 3. Syntax and function reference
The examples use the modern, public APIs. A function's exact signature can vary by library version.

| Function / method | What it does |
|---|---|
| ``geopandas.read_file`` | Load vector geospatial data. |
| ``.to_crs`` | Transform coordinate reference system. |
| ``.plot`` | Plot geometries. |
| ``.sjoin`` | Spatial join. |
| ``.area`, `.distance`` | Measure geometry properties in a suitable projected CRS. |
| ``folium.Map`` | Create a Leaflet map. |
| ``folium.Marker`, `CircleMarker`` | Add point markers. |
| ``GeoJson`` | Display GeoJSON layers. |
| ``Choropleth`` | Color geographic regions by values. |
| ``LayerControl`` | Toggle map layers. |

### Parameters
Parameters depend on the function; see the function reference table below and the official API documentation for version-specific details.

For every call, check the input type, axis, missing-value behavior, return type, and whether the operation changes the original object. Use `help(function)` or `function?` in a notebook to inspect the installed version.

## 4. Basic examples with outputs
```python
import folium
m = folium.Map(location=[22.57, 88.36], zoom_start=11)
folium.Marker([22.57, 88.36], tooltip="Kolkata").add_to(m)
m
```

## 5. Advanced examples
```python
# GeoPandas example (requires a valid local vector dataset)
# import geopandas as gpd
# gdf = gpd.read_file("districts.geojson")
# gdf = gdf.to_crs("EPSG:3857")  # choose CRS suitable for your task
# gdf.plot(column="population", legend=True)
```

## 6. Practical real-world applications
Map store locations, public service access, transport routes and region-level metrics.

## 7. Common mistakes
Calculating area/distance in longitude-latitude degrees; mixing CRS; using raw coordinates without checking order (latitude, longitude); misleading choropleth bins.

## 8. Practice questions
Create a Folium marker map; load a GeoJSON; reproject before measuring area; create a choropleth.

## 9. Interview questions
What is a CRS? Why reproject? Difference between point map and choropleth?

## 10. Related functions and concepts
GeoJSON, spatial joins, Plotly maps, geocoding and map ethics.
