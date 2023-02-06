<template>
  <div style="height:300px; width:450px">
    <l-map ref="map" v-model:zoom="zoom" :center="[45.7667, 4.7667]">
      <l-tile-layer
          url="https://{s}.tile.thunderforest.com/landscape/{z}/{x}/{y}.png?apikey=dab2d9119b7b4804944627b9a32950ed"
          layer-type="base"
          name="OpenStreetMap"
      ></l-tile-layer>
      <div v-for="city in cities">
        <div v-if="city.meteo === 'soleil'">
          <l-marker :lat-lng="city.longlat" :icon="iconSun"></l-marker>
        </div>
        <div v-if="city.meteo === 'couvert'">
          <l-marker :lat-lng="city.longlat" :icon="iconCloud"></l-marker>
        </div>
        <div v-if="city.meteo === 'pluie'">
          <l-marker :lat-lng="city.longlat" :icon="iconRain"></l-marker>
        </div>
      </div>
    </l-map>
  </div>
</template>

<script>
import "leaflet/dist/leaflet.css";
import {LMap, LTileLayer, LMarker, LIcon} from "@vue-leaflet/vue-leaflet";

const urlMeteo = 'https://api.openweathermap.org/data/2.5/find?lat=45.758&lon=4.765&cnt=20&cluster=yes&lang=fr&units=metric&APPID=32ca9eba476d69dd60c99ca49988792b'
export default {
  components: {
    LMap,
    LTileLayer,
    LMarker
  },
  data() {
    return {
      zoom: 11,
      cities: [],
      weather: [],
      loading: false,
      error: null,
      iconSun: L.icon({
        iconUrl: '/node_modules/leaflet/dist/images/soleil.png',
        iconSize: [32, 37],
        iconAnchor: [16, 37]
      }),
      iconCloud: L.icon({
        iconUrl: '/node_modules/leaflet/dist/images/nuage.png',
        iconSize: [32, 37],
        iconAnchor: [16, 37]
      }),
      iconRain: L.icon({
        iconUrl: '/node_modules/leaflet/dist/images/pluie.png',
        iconSize: [32, 37],
        iconAnchor: [16, 37]
      }),
      staticAnchor: [16, 37],
      customText: 'Foobar',
      iconSize: 64
    };
  },
  created() {
    this.fetchWeatherData()
  },
  methods: {
    async fetchWeatherData() {
      try {
        this.loading = true
        const response = await fetch(urlMeteo)
        const data = await response.json()
        for await (const city of data.list) {
          this.cities.push(
              {
                longlat: city.coord,
                meteo: city.weather[0].description
              }
          )
        }
        // console.log(this.cities)
        this.loading = false
      } catch (error) {
        this.error = true
        console.error(error)
      }
    }
  }
};

</script>

<style scoped>
#map :deep(.leaflet-marker-icon) {
  /*Impossible de changer un truc*/
  /*content: url("https://leafletjs.com/examples/custom-icons/leaf-green.png");*/
}

</style>