---
title: "Mapas Leaflet"
date: 2017-01-05
weight: 26
description: 
  
---


{{% pageinfo %}}
Inserción de mapas con [Leaflet](https://leafletjs.com/)

{{% /pageinfo %}}

## Requisitos

Leaflet necesita un css y un js

### css

```html
 <script src="https://unpkg.com/leaflet@1.9.1/dist/leaflet.js"
   integrity="sha256-NDI0K41gVbWqfkkaHj15IzU7PtMoelkzyKp8TOaFQ3s="
   crossorigin=""></script>
```

### js
 
```html
<script src="https://unpkg.com/leaflet@1.9.1/dist/leaflet.js"
   integrity="sha256-NDI0K41gVbWqfkkaHj15IzU7PtMoelkzyKp8TOaFQ3s="
   crossorigin=""></script>
```
### Div en el html

```html
 <div id="map"></div>
 ```

 ### Altura del div en el css

 ```css
 #map { height: 240px; }
 ```

### Cargar el mapa en el js

Si tenemos las variables **lat** y **lon** en en el **frontmatter** de la página con las coordenadas del mapa, podemos cargar el mapa con el siguiente código:

```js
var map = L.map('map').setView([{{ .Params.lat }}, {{ .Params.lon }}], 13);

L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
}).addTo(map);

L.marker([{{ .Params.lat }}, {{ .Params.lon }}
]).addTo(map)
    .bindPopup('{{ .Title }}');

```
