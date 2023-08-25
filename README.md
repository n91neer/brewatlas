# brewatlas
Helloworld

<html>
<head>
<meta charset="utf-8" />
<script src="https://api.mapbox.com/mapbox-gl-js/v2.0.0/mapbox-gl.js"></script>
<link href="https://api.mapbox.com/mapbox-gl-js/v2.0.0/mapbox-gl.css" rel="stylesheet" />

<!--style>
body { margin: 0; padding: 0; }
#map { position: absolute; top: 0; bottom: 0; width: 100%; }
</style-->
</head>

  
<body>

<style>
.mapboxgl-ctrl-pitchtoggle-3d {
    background-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMCIgaGVpZ2h0PSIzMCI+ICAgIDx0ZXh0IHg9IjUwJSIgeT0iNTAlIiBkeT0iLjM1ZW0iIHN0eWxlPSJmb250LXNpemU6IDE0cHg7IGZvbnQtZmFtaWx5OiAnSGVsdmV0aWNhIE5ldWUnLEFyaWFsLEhlbHZldGljYSxzYW5zLXNlcmlmOyBmb250LXdlaWdodDogYm9sZDsgdGV4dC1hbmNob3I6IG1pZGRsZTsiPjNEPC90ZXh0Pjwvc3ZnPg==);}
.mapboxgl-ctrl-pitchtoggle-2d {
    background-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIzMCIgaGVpZ2h0PSIzMCI+ICAgIDx0ZXh0IHg9IjUwJSIgeT0iNTAlIiBkeT0iLjM1ZW0iIHN0eWxlPSJmb250LXNpemU6IDE0cHg7IGZvbnQtZmFtaWx5OiAnSGVsdmV0aWNhIE5ldWUnLEFyaWFsLEhlbHZldGljYSxzYW5zLXNlcmlmOyBmb250LXdlaWdodDogYm9sZDsgdGV4dC1hbmNob3I6IG1pZGRsZTsiPjJEPC90ZXh0Pjwvc3ZnPg==);} 
</style>
    

<div id='map' style='width: 100%; height: 100vh;'></div>    
    
<script> 
	mapboxgl.accessToken = 'pk.eyJ1IjoiZXBpaGlrZSIsImEiOiJja2RjemszdmMwN2Q2MnFucjFiY3diYTExIn0.yMxerasstTOUqTLlqJcxow';
  
// Variable: Map  
var map = (window.map = new mapboxgl.Map({
	container: 'map',
  //style: 'mapbox://styles/epihike/ckpgtzkwl00ju17pdec4vto47', // Monochrome
	style: 'mapbox://styles/epihike/ckpprkwjd191k18pjws8bgodr', // San Francisco
  //style: 'mapbox://styles/epihike/ckm7zdamjghy717l994oe4s9o', // Oregon
	center: {{wf {&quot;path&quot;:&quot;location-long-lat&quot;,&quot;type&quot;:&quot;PlainText&quot;\} }},
	pitch: 0,
	zoom: {{wf {&quot;path&quot;:&quot;mapbox-zoom&quot;,&quot;type&quot;:&quot;Number&quot;\} }},
  minZoom: 2,
	bearing: 0, 
  interactive: true,
}));



  
//3D Toggle
class PitchToggle {
  constructor({bearing = -15, pitch = 25}) {
    this._bearing = bearing;
    this._pitch = pitch;}

  onAdd(map) {
    this._map = map;
    let _this = this;

    this._btn = document.createElement("button");
    this._btn.className = "mapboxgl-ctrl-pitchtoggle-3d";
    this._btn.type = "button";
    this._btn["aria-label"] = "Toggle Pitch";
    this._btn.onclick = function() {
      if (map.getPitch() === 0) {
        let options = { pitch: _this._pitch, bearing: _this._bearing };
        map.easeTo(options);
        _this._btn.className =
          "mapboxgl-ctrl-icon mapboxgl-ctrl-pitchtoggle-2d";
        map.setStyle('mapbox://styles/epihike/ckiukq7s12z6q19qm8ijuhund');
      } else {
        map.easeTo({ pitch: 0, bearing: 0 });
        _this._btn.className =
          "mapboxgl-ctrl-icon mapboxgl-ctrl-pitchtoggle-3d";
        map.setStyle('mapbox://styles/epihike/ckpprkwjd191k18pjws8bgodr');
      }
    };

    this._container = document.createElement("div");
    this._container.className = "mapboxgl-ctrl-group mapboxgl-ctrl";
    this._container.appendChild(this._btn);

    return this._container;}

  onRemove() {
    this._container.parentNode.removeChild(this._container);
    this._map = undefined;}}
  
map.addControl(new PitchToggle({/*minpitchzoom: 0*/}), "top-right");
 
 

map.addControl(new mapboxgl.NavigationControl(), 'top-right');
map.addControl(new mapboxgl.GeolocateControl( {
positionOptions: {
  enableHighAccuracy: true},
  trackUserLocation: true,
}), 'top-right');
 
</script>
 
</body>
</html>
