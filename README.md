# historical-map-groundtruth-25
This repository contains the ground-truth files from google drive 2017NEH-Map-Processing/maps/all-maps-for-transcribing

The google drive foler contains 26 folders as `USGS-15-CA-paloalto-e1899-s1895-rp1911` is duplicated.

The maps come from two sources: USGS and Ordinance survey. The ones that hve USGS as prefix in the name are from USGS and the ones use numerical string as names are Ordinance survey maps. 15 of them are USGS maps and 10 of them are Ordinance survey maps. 

`USGS-15-CA-hesperia-e1902-s1898-rp1912.shp` is not readable by python because of missing corresponding dbf file.

The historical Ordinance Survey maps were retrieved from National Library of Scotland (http://maps.nls.uk). The US historical maps were retrieved from Dr. Jerod Weinman's map processing project at Grinnell Coledge (http://www.cs.grinnell.edu/~weinman/research/maps.shtml), which were originally archived in the David Rumsey Map Collection (http://www.davidrumsey.com).

## How to read groundtruth

The ground truth of the map text is stored in .shp file format which can be loaded by ArcGIS or QGIS. They can be read and processed by python as well:

```
sf = shapefile.Reader('test.shp')   
shapes = sf.shapes()  
recds = sf.records() 
```

## Questions?
Please direct your questions to: yaoyichi@gmail.com
