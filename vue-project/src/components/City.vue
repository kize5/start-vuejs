<template>
  <div class="container">
  <h2> {{ name }} </h2>
  <p> {{ weather }}</p>
  <p> {{ temperature }}</p>
  <p> {{ updatedAt }}</p>
  </div>

</template>

<script>
export default {
  props: {
    name: String, // nom de la ville
    weather: String, // descriptif météo
    temperature: Number + String, // température en °C
    updatedAt: String// date de dernière mise à jour
  },
  data() {
    return {

    }
  }
}
</script>

<style scoped>

.container {
 margin: 5px;
}
</style>