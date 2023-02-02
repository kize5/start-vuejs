<template>
<h1>Météo actuel de ma ville</h1>
  <p> {{ name }}</p>
  <p> {{ weather }}</p>
  <p> {{ temperature }}</p>
  <p> {{ updatedAt }}</p>
</template>

<script>
export default {
  data() {
    return {
      name: 'Rumilly', // nom de la ville
      weather: 'Soleil de dingue', // descriptif météo
      temperature: 20.55 + "°", // température en °C
      updatedAt: new Date().toLocaleString()// date de dernière mise à jour
    }
  }
}
</script>

<style scoped>

</style>