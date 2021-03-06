# Visualization Data

This contains information that is generally useful for visualization
purposes. It started off mainly by pulling data from d3.js's examples and
then adding in general data as it was found. Below, are some comments
on each data set. This is a sister project to the [d3.js-boilerplate](https://github.com/zmaril/d3.js-boilerplate)
in terms of scope and purpose. 

## World Boundaries

These are derived from the public domain [Natural Earth](http://www.naturalearthdata.com/downloads/) cultural vector files, 110m resolution. Then, ogr2ogr was used to convert to GeoJSON. Lastly, the data was cleaned up slightly, removing extra properties and a degenerate edge from Antarctica.

 collection.features.forEach(function(d, i) {
   d.id = d.properties.ISO_A3;
   d.properties = {name: d.properties.SOVEREIGNT};
 });

## United States Boundaries

These are derived from the cartographic boundary files from the 2000
[U.S. Census](http://www.census.gov/geo/www/cob/bdy_files.html
). Then, MapShaper was used to simplify the geometry, and ogr2ogr to
convert the shapefiles to GeoJSON. Some additional work was done to
preserve the FIPS codes, which are dropped from the shapefiles by
MapShaper.
