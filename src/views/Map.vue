<template>
  <div>
    <h1>My Map</h1>
    <div class="mapContainer">
      <div ref="container" class="map"></div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import mapboxgl from "mapbox-gl";

export default {
  name: "Map",

  data: function () {
    return {
      commutes: [],
    };
  },

  mounted: async function () {
    mapboxgl.accessToken =
      "pk.eyJ1IjoidGlubzk3IiwiYSI6ImNrdzNpOWtzMTA3OGkzMW52dGZmbWw1cm0ifQ.FUovyoQJgf2jkCvZqWImvg";
    new mapboxgl.Map({
      container: this.$refs.container, // container ID
      style: "mapbox://styles/tino97/ckw3ifbpz206x14nqk6ranht9", // style URL
      center: [-74.5, 40], // starting position [lng, lat]
      zoom: 9, // starting zoom
    });
  },
};
</script>

<style src="mapbox-gl/dist/mapbox-gl.css"></style>

<style scoped>
.map {
  height: 50vh;
  width: 50vw;
}
.mapContainer {
  display: flex;
  justify-content: center;
  align-content: center;
}
</style>
