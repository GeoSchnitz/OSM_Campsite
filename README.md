OSM_Campsite
============

Test Project to show OSM Campsites on a Map
It's just a colletion of Ideas right now.

1. How to get the Data: 
http://www.geometrico.lu/osm2web/export/points/tourism/camp_site.geojson?bbox=12.99326,41.683,21.255,46.689&srid=4326
http://harrywood.co.uk/maps/uixapi/xapi.html

2. Openlayers 

var layer = new OpenLayers.Layer.Vector(
     'Campsites',
     {
         'strategies': [
             new OpenLayers.Strategy.BBOX()
         ],
         'protocol': new OpenLayers.Protocol.HTTP({
             'url': 
'http://www.geometrico.lu/osm2web/export/points/tourism/camp_site.geojson?',
             'format': new OpenLayers.Format.GeoJSON(),
             'params': { 'srid': 2169 }
         })
     }
); 


Another example:
http://overpass-api.de/open_layers_mashup.html

