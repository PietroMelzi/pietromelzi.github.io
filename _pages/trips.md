---
layout: page
title: Trips
permalink: /trips/
description: Some of the best places I’ve visited so far
nav: false
map: true
---

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
      { coords: [-7.7029, -79.4419], label: 'Puerto Malabrigo, Peru' },
      { coords: [-7.8136, -78.0463], label: 'Huamachuco, Peru' },
      { coords: [36.5271, -6.2886], label: 'Cadiz, Spain' },
      { coords: [36.6850, -6.1260], label: 'Jerez de la Frontera, Spain' },
      { coords: [36.0140, -5.6044], label: 'Tarifa, Spain' },
      { coords: [37.1773, -3.5986], label: 'Granada, Spain' },
      { coords: [43.3619, -5.8494], label: 'Asturias, Spain' },
      { coords: [39.6022, -9.0707], label: 'Nazare, Portugal' },
      { coords: [41.1579, -8.6291], label: 'Porto, Portugal' },
      { coords: [42.2205, -8.9066], label: 'Islas Cies, Spain' },
      { coords: [43.4615, -3.7353], label: 'Somo, Spain' },
      { coords: [43.3183, -1.9812], label: 'San Sebastian, Spain' },
      { coords: [42.8467, -2.6716], label: 'Vitoria-Gasteiz, Spain' },
      { coords: [42.7737, -0.3606], label: 'Formigal, Spain' },
      { coords: [41.9794, 2.8214], label: 'Girona, Spain' },
      { coords: [40.9429, -4.1088], label: 'Segovia, Spain' },
      { coords: [39.8628, -4.0273], label: 'Toledo, Spain' },
      { coords: [40.9701, -5.6635], label: 'Salamanca, Spain' },
      { coords: [39.4699, -0.3763], label: 'Valencia, Spain' },
      { coords: [40.7870, -4.0033], label: 'Navacerrada, Spain' },
      { coords: [43.5804, 7.1251], label: 'Antibes, France' },
      { coords: [48.0790, 7.3585], label: 'Colmar, France' },
      { coords: [47.3769, 8.5417], label: 'Zurich, Switzerland' },
      { coords: [46.4312, 6.9107], label: 'Montreux, Switzerland' },
      { coords: [45.8969, 8.5542], label: 'Isola dei Pescatori, Italy' },
      { coords: [45.6983, 9.6773], label: 'Bergamo, Italy' },
      { coords: [46.4680, 10.3722], label: 'Bormio, Italy' },
      { coords: [46.5386, 10.1335], label: 'Livigno, Italy' },
      { coords: [45.8856, 10.8412], label: 'Riva del Garda, Italy' },
      { coords: [45.6495, 13.7768], label: 'Trieste, Italy' },
      { coords: [46.3683, 14.1146], label: 'Lake Bled, Slovenia' },
      { coords: [43.9424, 12.4578], label: 'San Marino, San Marino' },
      { coords: [43.7696, 11.2558], label: 'Firenze, Italy' },
      { coords: [43.4019, 10.8615], label: 'Volterra, Italy' },
      { coords: [38.6743, 15.8980], label: 'Tropea, Italy' },
      { coords: [40.9955, 17.2180], label: 'Polignano a Mare, Italy' },
      { coords: [40.5579, 8.3193], label: 'Alghero, Italy' },
      { coords: [46.2594, 8.8352], label: 'Valle Verzasca, Switzerland' },
      { coords: [44.1194, 15.2314], label: 'Zadar, Croatia' },
      { coords: [44.4410, 15.0540], label: 'Pag Island, Croatia' },
      { coords: [48.1351, 11.5820], label: 'Munich, Germany' },
      { coords: [49.4521, 11.0767], label: 'Nuremberg, Germany' },
      { coords: [49.3988, 8.6724], label: 'Heidelberg, Germany' },
      { coords: [51.3811, -2.3590], label: 'Bath, United Kingdom' },
      { coords: [51.4545, -2.5879], label: 'Bristol, United Kingdom' },
      { coords: [50.8225, -0.1372], label: 'Brighton, United Kingdom' },
      { coords: [52.1400, -10.2686], label: 'Dingle, Ireland' },
      { coords: [61.0986, 7.4822], label: 'Luster, Norway' },
      { coords: [57.7089, 11.9746], label: 'Goteborg, Sweden' },
      { coords: [59.3293, 18.0686], label: 'Stockholm, Sweden' },
      { coords: [7.7407, 98.7784], label: 'Phi Phi Island, Thailand' },
      { coords: [36.0133, 14.3236], label: 'Blue Lagoon, Malta' },
      { coords: [36.0443, 14.2512], label: 'Gozo, Malta' },
      { coords: [9.3924, -84.1398], label: 'Manuel Antonio, Costa Rica' },
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
