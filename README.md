# HROK Sydney - Vietnam map demo with OpenLayers #

**[OpenLayers](http://openlayers.org "OpenLayers")** is an opensource javascript library that "makes it easy to put a dynamic map in any web page". 


The good thing about OpenLayers is that you can combine multiple map sources (Google, Bing, Yahoo, ESRI, OpenStreetMap) as well as a custom maps... something you couldn't do if you used say the Google Maps SDK alone. OpenLayers also simply provided HEAPS of functionality that would take you forever to code in javascript & jquery/ext otherwise.



This demo uses Google plus a some custom maps I have set up. It very briefly shows how OpenLayers can be used to;

1. put a point on a map 
1. shade a region on map

<br/>
**Custom Base Maps**<br/>
For custom maps I set up Rackspace Cloud Server with Ubuntu and installed **[GeoServer](http://geoserver.org/ "GeoServer")**. 

*"GeoServer is an open source software server written in Java that allows users to share and edit geospatial data. Designed for interoperability, it publishes data from any major spatial data source using open standards."*

GeoServer can serve map tile **images** or **xml**... plus stuff like GML, KML and more.

<br/>
**Spatial Data**<br/>
Spatial data usually referred to by administrative level<br/>
0 - Country<br/>
1 - State/District<br/>
2 - Municipality/Province<br/>
3 - Ward/District

Vietnam is a divided into regions, provinces & districts. Australia of course is states, municipalities & wards. 

We get is opensource GIS data from [http://www.gadm.org/](http://www.gadm.org/ "GADM"). 

<br/>
**Geek Alert!**<br/>
Spatial Databases are cool! Once you have your spatial data in you can do things like...
    
    // select ID for records within 10 meters of polygon A
	SELECT 		A.GID 
    FROM 		POLYGONS A 
    WHERE 		SDO_WITHIN_DISTANCE(A.Geometry, :aGeom, 'distance = 10') = 'TRUE';