<template>
  <div class="home">
    <div id="map"></div>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted } from 'vue';
// import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import Map from 'ol/Map';
import View from 'ol/View';
import TileLayer from 'ol/layer/Tile';
import XYZ from 'ol/source/XYZ';

export default defineComponent({
  name: 'Home',
  // components: {
  //   HelloWorld,
  // },
  setup() {
    onMounted(() => {
      console.log('bbb');
    
      new Map({
        target: 'map',
        layers: [
          new TileLayer({
            source: new XYZ({
              url: 'https://{a-c}.tile.openstreetmap.org/{z}/{x}/{y}.png'
            })
          })
        ],
        view: new View({
          center: [0, 0],
          zoom: 2
        })
      });
    })
  },
});
</script>

<style lang="scss" scoped>
#map{
  height: 400px;
}
</style>
