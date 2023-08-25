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
#map { position: absolute; top: 150px; bottom: 0; width: 100%; }
</style>
</head>
<body>
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
  
// Add zoom and rotation controls to the map.
map.addControl(new mapboxgl.NavigationControl());
  
// Add a scale control to the map
map.addControl(new mapboxgl.ScaleControl());  
  
</script>

</body>
</html>
