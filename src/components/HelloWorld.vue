<script setup>
import { onMounted, ref } from 'vue'
// import { Viewer } from 'cesium';
import * as Cesium from 'cesium';
onMounted(() => {
  const dxt = new Cesium.UrlTemplateImageryProvider({
    url: "https://t0.tianditu.gov.cn/mapservice/swdx?tk=0326461d186c59cafc7df93e69a814d8",
    subdomains: ['0', '1', '2', '3', '4', '5', '6', '7'],
    tilingScheme: new Cesium.WebMercatorTilingScheme(),
    maximumLevel: 18
  })
  const viewer = new Cesium.Viewer('mapContainer', {
    baseLayerPicker: false,
    // imageryProvider: dxt
  });

})
defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <div id="mapContainer">

  </div>
</template>

<style scoped>
#mapContainer {
  widows: 100%;
  height: 100%;
}
</style>
