
<template>
  <div class="example">
  <l-map
    :zoom="initialZoom"
    :center="initialLocation">
    <l-iiif
      :url="infoUrl"
      :options="opts"/>
  </l-map>
  </div>
</template>

<script>
import * as L from 'leaflet'
import { LMap } from 'vue2-leaflet'
import LIiif from '../src/Vue2LeafletIIIF'
const iiifOptions = {
    tileFormat: 'jpg',
    tileSize: 512,
}
export default {
  components: {
    LMap,
    LIiif
  },
  data () {
    return {
      initialLocation: L.latLng(0, 0),
      initialZoom: 2,
      opts: iiifOptions,
      infoUrl: "http://iiif.hualab.nl:8080/iiif/2/saftleven-panorama-1684.jpg/info.json"
    }
  }
}
</script>

<style>
  @import "https://unpkg.com/leaflet@1.6.0/dist/leaflet.css";
  html, body {
    margin: 0;
    height: 100%;
  }
  .example {
    height: 100%;
    width: 100%;
  }
</style>