<template>
  <div id="map" style="width: 100%; height: 900px"></div>
</template>

<script>
import Map from 'ol/Map';
import OSM from 'ol/source/OSM';
import TileLayer from 'ol/layer/Tile';
import View from 'ol/View';

export default {
  name: 'About',
  mounted() {
    this.init();
  },
  methods: {
    init() {
      const map = new Map({
        layers: [
          new TileLayer({
            source: new OSM(),
          }),
        ],
        target: 'map',
        view: new View({
          center: [0, 0],
          zoom: 2,
        }),
      });
    },
  },
};
</script>

<style>
#map:focus {
  outline: #4a74a8 solid 0.15em;
}
</style>
