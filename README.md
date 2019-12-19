# Kentucky Mine Sites
Create map with past and present mine sites across the state of Kentucky at zoom level for state extents . Select sites that are currently active surface mine and zoom to one site to display Landsat imagery of present and past to show landscape destruction.

Data:
1. Kentucky point data created from [Kentucky Mine Mapping Information System](http://minemaps.ky.gov/Default.aspx?Src=Downloads)
2. Landsat imagery from [Earth Explorer](https://earthexplorer.usgs.gov/)

Processing Data:
1. [Processing satellite imagery](https://docs.mapbox.com/help/tutorials/processing-satellite-imagery/) tutorial for Landsat stacking bands to one tif files. Using Path:19 Row:34

Problems with code in processing [Landsat 5 imagery tutorial](https://docs.mapbox.com/help/tutorials/processing-satellite-imagery/)
  1. rio stack command
     brackets will no work for the file name {3,2,1} to read file into raster set must be typed out completely
  2. rio warp EPSG:3857 give error proj.db not found can use projection type to run command
      "+proj=merc +a=6378137 +b=6378137 +lat_ts=0.0 +lon_0=0.0 +x_0=0.0 +y_0=0 +k=1.0 +units=m +nadgrids=@null +wktext  +no_defs"
      found at [epsg.io](https://epsg.io/3857)
  3. rio color no binaries for Window OS to run
     [error rio color](https://github.com/mapbox/rio-color/issues/46)
