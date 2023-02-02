<template>

  <h1>Météo des villes :</h1>
  <!--  <City />-->
  <div v-for="city in cities" class="loop">
    <City :name=city.name />
    <City :weather=city.weather />
    <City :temperature=city.temperature />
    <City :updated-at=city.updatedAt.toLocaleString() />
  </div>
</template>

<script>
import City from "@/components/City.vue";

export default {
  components: {
    City
  },
  data() {
    return {
      cities: [
        {
          id: 1,
          name: 'Rumilly',
          weather: 'Ensoleillé',
          temperature: 22.0,
          updatedAt: new Date()
        },
        {
          id: 2,
          name: 'Alby-sur-Chéran',
          weather: 'Peu nuageux',
          temperature: 19.5,
          updatedAt: new Date()
        },
        {
          id: 3,
          name: 'Annecy',
          weather: 'Nuageux',
          temperature: 21.5,
          updatedAt: new Date()
        }
      ]
    }
  }
}
</script>

<style scoped>
.loop {
  display: flex;
  flex-direction: column;
  align-content: center;
  border: solid black 1px;
  margin: 10px;
  justify-content: center;
  align-items: center;
}
</style>