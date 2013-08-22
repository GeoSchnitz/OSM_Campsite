OSM_Campsite
============

Test Project to show OSM Campsites on a Map
It's just a colletion of Ideas right now.

1. How to get the Data: 
http://www.geometrico.lu/osm2web/export/points/tourism/camp_site.geojson?bbox=12.99326,41.683,21.255,46.689&srid=4326
http://harrywood.co.uk/maps/uixapi/xapi.html

Data with Overpass API 
http://overpass-turbo.eu/?Q=%3Cunion%3E%0A%20%20%3Cquery%20type%3D%22node%22%3E%0A%20%20%20%20%3Chas-kv%20k%3D%22tourism%22%20v%3D%22camp_site%22%2F%3E%0A%20%20%20%20%3Cbbox-query%20%7B%7Bbbox%7D%7D%2F%3E%0A%20%20%3C%2Fquery%3E%0A%20%20%0A%3C%2Funion%3E%0A%3Cprint%2F%3E&C=44.97257;15.54016;7


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

