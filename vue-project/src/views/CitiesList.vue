<template>
<div class="container">
  <h1>Météo des villes :</h1>
  <p>Date : {{ date }}</p>
  <!--  <City />-->
  <div v-for="city in cities" class="loop">
    <p><City :name=city.name /></p>
    <p><City :weather=city.weather /></p>
    <p><City :temperature=city.temperature /></p>
    <p><City :temperature=city.wind /></p>
    <p><City :updated-at=city.updatedAt /></p>
  </div>

  <div class="div-error" v-if="error === true">
    <p>Fail load API!</p>
  </div>
  <div class="div-loading" v-if="loading === true">
    <p>Requête en cours</p>
  </div>

</div>
</template>

<script>
import City from "@/components/City.vue";
import { format } from 'timeago.js';

const urlMeteo = 'https://api.openweathermap.org/data/2.5/find?lat=45.758&lon=4.765&cnt=20&cluster=yes&lang=fr&units=metric&APPID=32ca9eba476d69dd60c99ca49988792b'

export default {
  components: {
    City
  },
  data() {
    return {
      date: new Date().toLocaleString(),
      cities: [],
      loading: false,
      error: null,
    }
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
        for await (const city of data.list)
        {this.cities.push(
          {
            id: 0,
            name: city.name,
            weather: city.weather[0].description,
            temperature: "Température : " +(city.main.temp).toFixed(1)+"°",
            wind: "Vitesse du vent : " + city.wind.speed,
            updatedAt: format(Date.now() - 10 * 60 * 60),
          }
        )
        }
        this.loading =false
      } catch (error) {
        this.error=true
        console.error(error)
      }
    }
  }
}
</script>

<style scoped>

.div-error {
  display: flex;
  justify-content: center;
  align-items: center;
  background: lightcoral;
  min-width: 300px;
  max-width: 400px;
  height: 75px;
  border-radius: 20px;
  box-shadow: 12px 12px 2px 1px rgba(0, 0, 255, .2);
  border: solid black 2px;
  margin: 30px;
}

.div-loading {
  display: flex;
  justify-content: center;
  align-items: center;
  background: lightblue;
  min-width: 300px;
  max-width: 400px;
  height: 75px;
  border-radius: 20px;
  box-shadow: 12px 12px 2px 1px rgba(0, 0, 255, .2);
  border: solid black 2px;
  margin: 30px;
}

.container {
  display: flex;
  align-content: center;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  flex-direction: column;
}
.loop {
  max-width: 300px;
  min-width: 300px;
  display: flex;
  flex-direction: column;
  align-content: center;
  border: solid black 1px;
  margin: 15px;
  justify-content: center;
  align-items: center;
  backdrop-filter: blur(10px);
  box-shadow: 12px 12px 2px 1px rgba(0, 0, 255, .2);
  border-radius: 10px;
}
</style>