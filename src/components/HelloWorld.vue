<template>
  <div>
    <p>hi</p>
    <div id="map" class="map">
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: {
    map: null,
    tileLayer: null,
    layers: [

    ]
  },
  methods: {
    initMap() {
      this.map = L.map('map').setView([38,-98.5], 3.5);
      this.tileLayer = L.tileLayer(
          'https://cartodb-basemaps-{s}.global.ssl.fastly.net/rastertiles/voyager/{z}/{x}/{y}.png',
        {
          maxZoom: 18,
          attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>, &copy; <a href="https://carto.com/attribution">CARTO</a>',
        }
      );
this.tileLayer.addTo(this.map);
    },
    initLayers() {}
  },
  mounted() {
    this.initMap();
    this.initLayers();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
#map {
  height: 400px;
}
</style>
