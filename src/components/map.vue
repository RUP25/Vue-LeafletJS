<template>
  <div id="map"></div>
</template>

<script>
import L from "leaflet";

export default {
  name: "map",
  data() {
    return {
      map: null
    };
  },
  mounted() {
    var cities = L.layerGroup();

    L.marker([25.5788, 91.8933])
      .bindPopup("This is Shillong, CO.")
      .addTo(cities),
      L.marker([26.1445, 91.7362])
        .bindPopup("This is Guwahati, CO.")
        .addTo(cities),
      L.marker([23.7307, 92.7173])
        .bindPopup("This is Aizwal, CO.")
        .addTo(cities),
      L.marker([23.8315, 91.2868])
        .bindPopup("This is Agartala, CO.")
        .addTo(cities);

    var grayscale = L.tileLayer(
      "https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw",
      {
        maxZoom: 18,
        attribution:
          'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, ' +
          '<a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
          'Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
        id: "mapbox/streets-v9",
        tileSize: 512,
        zoomOffset: -1
      }
    );
    var streets = L.tileLayer(
      "https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw",
      {
        maxZoom: 18,
        attribution:
          'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, ' +
          '<a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
          'Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
        id: "mapbox/streets-v11",
        tileSize: 512,
        zoomOffset: -1
      }
    );
    var map = L.map("map", {
      center: [25.5736, 93.2473],
      zoom: 7,
      layers: [grayscale, cities]
    });
    var baseLayers = {
      Grayscale: grayscale,
      Streets: streets
    };

    var overlays = {
      Cities: cities
    };

    L.control.layers(baseLayers, overlays).addTo(map);
  },
  beforeDestroy() {
    if (this.map) {
      this.map.remove();
    }
  }
};
</script>

<style>
#map {
  width: 100vw;
  height: 100vh;
}
</style>
