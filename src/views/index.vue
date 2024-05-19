
<template>
  <div class="wrap">
    <div ref="mapContainer" id="map"></div>

  </div>
</template>

<script lang="ts" setup>
  import mapboxgl from 'mapbox-gl'
  const mapContainer = ref(null)
  const initMap = () => {
      mapboxgl.accessToken =
          'pk.eyJ1Ijoib25pc205IiwiYSI6ImNsaGV6empibDAzd3gzdHBmeGd2bDAwYWkifQ.gjhG1z8Uo8bZETQuRn3Stg'
      const map = new mapboxgl.Map({
          container: mapContainer.value,
          center: [0, 0], // starting position [lng, lat]
          zoom: 9 // starting zoom
      })

      map.addControl(new mapboxgl.NavigationControl())
  }
  onMounted(() => {
      initMap()
  })
</script>
<style lang="scss" scoped>
  .wrap {
      height: 100vh;
      width: 100vw;
      #map {
          height: 100vh;
          width: 100vw;
      }
  }
</style>