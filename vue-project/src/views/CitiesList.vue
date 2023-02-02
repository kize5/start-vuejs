
<template>

<h1>Météo des villes :</h1>
  <City />
  <City name="Annecy" />
  <City weather="Soleil" />
  <City temperature= 20° />
  <City :updatedAt= "new Date().toLocaleString()" />

</template>

<script>
import City from "@/components/City.vue";
export default {
  components :{
    City
  }
}
</script>

<style scoped>

</style>