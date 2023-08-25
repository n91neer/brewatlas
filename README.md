# brewatlas
🍻Brewatlas

<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Display a map on a webpage</title>
<meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no">
<link href="https://api.mapbox.com/mapbox-gl-js/v2.14.1/mapbox-gl.css" rel="stylesheet">
<script src="https://api.mapbox.com/mapbox-gl-js/v2.14.1/mapbox-gl.js"></script>
<style>
body { margin: 0; padding: 0; }
#map { position: absolute; top: 150px; bottom: 0; width: 100vw; }
</style>
</head>
<body>

<!-- Load the `mapbox-gl-geocoder` plugin. -->
<script src="https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-geocoder/v5.0.0/mapbox-gl-geocoder.min.js"></script>
<link rel="stylesheet" href="https://api.mapbox.com/mapbox-gl-js/plugins/mapbox-gl-geocoder/v5.0.0/mapbox-gl-geocoder.css" type="text/css">  
  
<div id="map"></div>
<script>
	mapboxgl.accessToken = 'pk.eyJ1IjoiZXBpaGlrZSIsImEiOiJja2RjemszdmMwN2Q2MnFucjFiY3diYTExIn0.yMxerasstTOUqTLlqJcxow';
    const map = new mapboxgl.Map({
        container: 'map', // container ID
        // Choose from Mapbox's core styles, or make your own style with Mapbox Studio
        style: 'mapbox://styles/epihike/cllqwamds008b01qyesd2cdzv', // style URL
        center: [12.0, 49.97], // starting position [lng, lat]
        zoom: 4 // starting zoom
    });
  
  
// Add a scale control to the map
map.addControl(new mapboxgl.ScaleControl());  

// Add the control to the map.
map.addControl(
new MapboxGeocoder({
accessToken: mapboxgl.accessToken,
mapboxgl: mapboxgl
})
);  

  // Add zoom and rotation controls to the map.
map.addControl(new mapboxgl.NavigationControl());

// Add geolocate control to the map.
map.addControl(
new mapboxgl.GeolocateControl({
positionOptions: {
enableHighAccuracy: true
},
// When active the map will receive updates to the device's location as it changes.
trackUserLocation: true,
// Draw an arrow next to the location dot to indicate which direction the device is heading.
showUserHeading: true
})
);  
  
</script>

</body>
</html>
