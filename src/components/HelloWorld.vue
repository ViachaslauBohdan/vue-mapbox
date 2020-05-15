<template>
<div>
  <div @click="loadMap()">
    <button>Click me</button>
  </div>
  <div style="width:1200px;height:1200px" v-if="showMap">
    <MglMap :accessToken="accessToken" :mapStyle="mapStyle" :mapboxGl="mapbox-gl" />
  </div>
</div>
</template>

<script>
// import Mapbox from "mapbox-gl";
import { MglMap } from "vue-mapbox";

export default {
  components: {
    MglMap
  },
  data() {
    return {
      accessToken: 'pk.eyJ1IjoiYXBhZGV2IiwiYSI6ImNrYTJnZWZjeTBhNHIzZHAwMjl3OGNtZmsifQ.fVVScoKaYNsms9DbXaKNpw', // your access token. Needed if you using Mapbox maps
      mapStyle: 'mapbox://styles/mapbox/streets-v11', // your map style
      showMap: false
    };
  },
  methods: {
    loadMap() {
      this.showMap = true
    }
  },

  created() {
    // We need to set mapbox-gl library here in order to use it in template
    // this.mapbox = Mapbox;
  }
};
</script>