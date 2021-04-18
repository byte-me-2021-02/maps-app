<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div id="map"></div>
  </div>
</template>

<style>
body { margin: 0; padding: 0; }
#map { position: absolute; top: 0; bottom: 0; width: 100%; }
</style>

<script>
/* global mapboxgl */

export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!"
    };
  },
  mounted: function() {
    mapboxgl.accessToken = process.env.VUE_APP_MAPBOX_KEY;
    var map = new mapboxgl.Map({
        container: 'map', // container id
        style: 'mapbox://styles/mapbox/streets-v11', // style URL
        center: [12.554729, 55.70651], // starting position [lng, lat]
        zoom: 2 // starting zoom
    });

    var marker1 = new mapboxgl.Marker()
    // .setLngLat([12.554729, 55.90651])
    .setLngLat([-78.8784, 42.8864])

    .addTo(map);
    
    // Create a default Marker, colored black, rotated 45 degrees.
    var marker2 = new mapboxgl.Marker({ color: 'black', rotation: 45 })
    .setLngLat([12.65147, 55.608166])
    .addTo(map);
  },
  methods: {}
};


</script>

