---
layout: page
title: Trips
permalink: /trips/
description: Places, routes, and highlights.
nav: false
map: true
---

<h2>Trips map</h2>
<p>
  Here is a world map with some of the best places I’ve visited so far. I’ll keep adding new pins and stories over time.
</p>

<div id="trips-map" style="height: 600px; max-width: 100%;"></div>

<div class="mt-3">
  <strong>Legend</strong>
  <div>
    <img
      src="https://raw.githubusercontent.com/pointhi/leaflet-color-markers/master/img/marker-icon-green.png"
      alt="Green marker"
      style="height: 18px; margin-right: 4px;"
    >
    <span>Places where I have lived</span>
  </div>
  <div>
    <img
      src="https://unpkg.com/leaflet@1.9.4/dist/images/marker-icon.png"
      alt="Blue marker"
      style="height: 18px; margin-right: 4px;"
    >
    <span>Places I have visited</span>
  </div>
</div>

<script>
  window.addEventListener('load', function () {
    if (typeof L === 'undefined') {
      return;
    }

    var map = L.map('trips-map').setView([20, 0], 2);

    L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
      maxZoom: 19,
      attribution:
        '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors',
    }).addTo(map);

    L.Icon.Default.mergeOptions({
      iconSize: [18, 30],
      iconAnchor: [9, 30],
      popupAnchor: [1, -28],
      shadowSize: [30, 30],
    });

    var redIcon = new L.Icon({
      iconUrl:
        'https://raw.githubusercontent.com/pointhi/leaflet-color-markers/master/img/marker-icon-red.png',
      shadowUrl:
        'https://unpkg.com/leaflet@1.9.4/dist/images/marker-shadow.png',
      iconSize: [18, 30],
      iconAnchor: [9, 30],
      popupAnchor: [1, -28],
      shadowSize: [30, 30],
    });

    var greenIcon = new L.Icon({
      iconUrl:
        'https://raw.githubusercontent.com/pointhi/leaflet-color-markers/master/img/marker-icon-green.png',
      shadowUrl:
        'https://unpkg.com/leaflet@1.9.4/dist/images/marker-shadow.png',
      iconSize: [18, 30],
      iconAnchor: [9, 30],
      popupAnchor: [1, -28],
      shadowSize: [30, 30],
    });

    var places = [
      { coords: [40.4168, -3.7038], label: 'Madrid, Spain', iconKey: 'green' },
      { coords: [-13.5320, -71.9675], label: 'Cusco, Peru' },
      { coords: [18.7883, 98.9853], label: 'Chiang Mai, Thailand' },
      { coords: [9.2516, -83.8670], label: 'Dominical, Costa Rica' },
      { coords: [29.0469, -13.5899], label: 'Lanzarote, Spain' },
      { coords: [67.8558, 20.2253], label: 'Kiruna, Sweden' },
      { coords: [45.9636, 9.2572], label: 'Lake Como, Italy', iconKey: 'green' },
      { coords: [58.4108, 15.6214], label: 'Linköping, Sweden', iconKey: 'green' },
      { coords: [52.5200, 13.4050], label: 'Berlin, Germany', iconKey: 'green' },
      { coords: [49.8728, 8.6512], label: 'Darmstadt, Germany', iconKey: 'green' },
      { coords: [35.1680, -2.9330], label: 'Nador, Morocco' },
      { coords: [40.7128, -74.0060], label: 'New York, USA' },
      { coords: [35.8989, 14.5146], label: 'Valletta, Malta' },
      { coords: [60.3913, 5.3221], label: 'Bergen, Norway' },
      { coords: [37.1019, -8.6742], label: 'Lagos, Portugal' },
      { coords: [53.2707, -9.0568], label: 'Galway, Ireland' },
      { coords: [41.9028, 12.4964], label: 'Rome, Italy' },
      { coords: [44.8378, -0.5792], label: 'Bordeaux, France' },
      { coords: [44.8800, 15.6167], label: 'Plitvice Lakes, Croatia' },
      { coords: [53.2194, 6.5665], label: 'Groningen, Netherlands' },
      { coords: [55.6761, 12.5683], label: 'Copenhagen, Denmark' },
      { coords: [51.0543, 3.7174], label: 'Ghent, Belgium' },
      { coords: [50.0755, 14.4378], label: 'Prague, Czech Republic' },
      { coords: [47.4979, 19.0402], label: 'Budapest, Hungary' },
      { coords: [59.4370, 24.7536], label: 'Tallinn, Estonia' },
      { coords: [44.1469, 9.6541], label: 'Cinque Terre, Italy' },
      { coords: [41.2120, 9.4125], label: 'La Maddalena, Italy' },
      { coords: [37.3891, -5.9845], label: 'Seville, Spain' },
      { coords: [39.3558, -9.3817], label: 'Peniche, Portugal' },
      { coords: [40.6663, 16.6043], label: 'Matera, Italy' },
      { coords: [40.8518, 14.2681], label: 'Naples, Italy' },
      { coords: [43.3188, 11.3308], label: 'Siena, Italy' },
      { coords: [45.4950, 10.6080], label: 'Sirmione, Italy' },
      { coords: [46.7967, 11.9343], label: 'Brunico, Italy' },
      { coords: [10.4717, -84.6453], label: 'La Fortuna, Costa Rica' },
      { coords: [8.0340, 98.8220], label: 'Ao Nang, Thailand' },
      { coords: [-15.8402, -70.0219], label: 'Puno, Peru' },
      { coords: [13.7563, 100.5018], label: 'Bangkok, Thailand' },
      { coords: [-12.0464, -77.0428], label: 'Lima, Peru' },
      { coords: [-8.1117, -79.0288], label: 'Trujillo, Peru' },
      { coords: [28.2916, -16.6291], label: 'Tenerife, Spain' },
    ];

    var iconByKey = {
      red: redIcon,
      green: greenIcon,
    };

    places.forEach(function (p) {
      var options = {};
      if (p.iconKey && iconByKey[p.iconKey]) {
        options.icon = iconByKey[p.iconKey];
      }
      L.marker(p.coords, options).addTo(map).bindPopup(p.label);
    });
  });
</script>
