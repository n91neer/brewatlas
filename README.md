# brewatlas
Helloworld

<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Display a web map using an alternate projection</title>
<meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no">
<link href="https://api.mapbox.com/mapbox-gl-js/v2.14.1/mapbox-gl.css" rel="stylesheet">
<script src="https://api.mapbox.com/mapbox-gl-js/v2.14.1/mapbox-gl.js"></script>
<style>
body { margin: 0; padding: 0; }
#map { position: absolute; top: 0; bottom: 0; width: 100%; }
</style>
</head>
<body>
<div id="map"></div>
<script>
	mapboxgl.accessToken = 'pk.eyJ1IjoiZXBpaGlrZSIsImEiOiJja2RjemszdmMwN2Q2MnFucjFiY3diYTExIn0.yMxerasstTOUqTLlqJcxow';
    const map = new mapboxgl.Map({
        container: 'map',
        // Choose from Mapbox's core styles, or make your own style with Mapbox Studio
        style: 'mapbox://styles/mapbox/streets-v12',
        center: [0, 0],
        zoom: 0.4,
        projection: 'naturalEarth' // starting projection
    });
</script>

</body>
</html>
