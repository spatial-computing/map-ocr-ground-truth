# map-ocr-ground-truth

This repository contains ten historical Ordinance Survey map examples, five historical US map examples, and their respective OCR ground truth.

The map sections used to create the ground truth are stored in the TIFF format in the folder **maps**. The maps with file name starting with 1920 are the Ordinance Survey maps. The others are US historical maps.

The historical Ordinance Survey maps were retrieved from National Library of Scotland (<http://maps.nls.uk>). The US historical maps were retrieved from Dr. Jerod Weinman's map processing project at Grinnell Coledge (<http://www.cs.grinnell.edu/~weinman/research/maps.shtml>), which were originally archived in the David Rumsey Map Collection (<http://www.davidrumsey.com>).

In this repository, the ground truth of map labels were created by the USC Spatial Computing Lab (<http://spatial-computing.github.io>) (licensed under the Apache License, Version 2.0), including effort from Yao-Yi Chiang, Narges Honarvar Nazari, Zexuan Luo, Rashmina Ramachandran Menon, Tian Xiang Tan, and Sima Moghaddam. 




## How to Read the Ground Truth
The ground truth of the map text is stored in two format: GeoJSON (<https://en.wikipedia.org/wiki/GeoJSON>) and Esri Shapefile (<https://en.wikipedia.org/wiki/Shapefile>)

The ground truth data in GeoJSON (.geojson files) are in the folder **map-labels->geojson**. The ground truth data in Shapefile (.shp, .shx, and .dbf files) are in the folder **map-labels->shapefile** 

In both format, the **geometry** of an entry ("feature") is a bounding polygon (usually a rectangle) of a word in a map. The geometry is in the image coordinates.

The **attributes (properties)** of each entry are as follows. Given a map word "Canewdon" that is a part of a compound word "Canewdon Hall", its ground truth entry is:

```
{ "type": "Feature", "properties": { "Label": "Canewdon", "Phrase": "Canewdon Hall", "Map": "1920_1", "Id": 1, "Group": 1 }, "geometry": { "type": "Polygon", "coordinates": [ [ [ 590.376315789473892, -556.057894736842059 ], [ 733.618421052631902, -556.057894736842059 ], [ 733.618421052631902, -588.884210526315769 ], [ 590.376315789473892, -588.884210526315769 ], [ 590.376315789473892, -556.057894736842059 ] ] ] } },
```
where:

* "Label": "Canewdon" - This is the ground truth of the map text
* "Phrase": "Canewdon Hall" -  This is the ground truth of the "phrase" or "compound word" that the label belongs to.
* "Id": 1 - This is the order in a phrase where the label appears.

Here is the ground truth entry for the word "Hall" in "Canewdon Hall":

```
{ "type": "Feature", "properties": { "Label": "Hall", "Phrase": "Canewdon Hall", "Map": "1920_1", "Id": 2, "Group": 1 }, "geometry": { "type": "Polygon", "coordinates": [ [ [ 623.202631578947603, -597.836842105263145 ], [ 709.744736842105567, -597.836842105263145 ], [ 709.744736842105567, -633.647368421052533 ], [ 623.202631578947603, -633.647368421052533 ], [ 623.202631578947603, -597.836842105263145 ] ] ] } },
```
Note that here the "Id" for "Hall" is 2 since "Hall" is the second word in the phrase "Canewdon Hall".

## Visualizing the Ground Truth
All maps and their ground truth data can be viewed using QGIS (<http://www.qgis.org/en/site/>). The easiest way for visualizing everything at once is using QGIS to open the file **groundtruth.qgs**.

##  Links for the maps in the David Rumsey Map Collection: 

<http://www.davidrumsey.com/luna/servlet/detail/RUMSEY~8~1~3350~410059:Florida->

<http://www.davidrumsey.com/luna/servlet/detail/RUMSEY~8~1~24434~890113:Map-of-the-Northern-Pacific-Railroa>

<http://www.davidrumsey.com/luna/servlet/detail/RUMSEY~8~1~24449~900011:Map-Of-Missouri->

<http://www.davidrumsey.com/luna/servlet/detail/RUMSEY~8~1~33765~1171481:Colorado->

<http://www.davidrumsey.com/luna/servlet/detail/RUMSEY~8~1~201696~3000661:South-Dakota->
 
A TIFF version of these maps can be found in the folder maps->original-scanned-historical-maps
##  Link for the Ordinance Survey maps:
<http://maps.nls.uk>
##  Questions?
Please direct your questions to: yaoyichi@gmail.com