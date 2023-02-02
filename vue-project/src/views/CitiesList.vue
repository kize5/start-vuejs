<template>
<div class="container">
  <h1>Météo des villes :</h1>
  <p>Date : {{ date }}</p>
  <!--  <City />-->
  <div v-for="city in cities" class="loop">
    <City :name=city.name />
    <City :weather=city.weather />
    <City :temperature=city.temperature />
    <City :updated-at=city.updatedAt />
  </div>
</div>
</template>

<script>
import City from "@/components/City.vue";
import { format, render, cancel, register } from 'timeago.js';

export default {
  components: {
    City
  },
  data() {
    return {
      date: new Date().toLocaleString(),
      cities: [
        {
          id: 1,
          name: 'Rumilly',
          weather: 'Ensoleillé',
          temperature: 22.0,
          updatedAt: format(Date.now() - 10 * 60 * 60),
        },
        {
          id: 2,
          name: 'Alby-sur-Chéran',
          weather: 'Peu nuageux',
          temperature: 19.5,
          updatedAt: format(Date.now() - 10 * 60 * 60),
        },
        {
          id: 3,
          name: 'Annecy',
          weather: 'Nuageux',
          temperature: 21.5,
          updatedAt: format(Date.now() - 10 * 60 * 60),
        }
      ]
    }
  }
}
</script>

<style scoped>

.container {
  display: flex;
  align-content: center;
  justify-content: center;
  flex-wrap: wrap;
  flex-direction: column;
}
.loop {
  max-width: 300px;
  display: flex;
  flex-direction: column;
  align-content: center;
  border: solid black 1px;
  margin: 10px;
  justify-content: center;
  align-items: center;
  backdrop-filter: blur(10px);
  box-shadow: 12px 12px 2px 1px rgba(0, 0, 255, .2);
}
</style>