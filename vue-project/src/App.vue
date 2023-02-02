<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Discover from "@/views/Discover.vue";
import CitiesList from "@/views/CitiesList.vue";
</script>

<template>
<!--  <header>-->
<!--    <div class="wrapper">-->
<!--      <nav>-->
<!--      </nav>-->
<!--    </div>-->
<!--  </header>-->

  <CitiesList />
  <main>
    <div class="container">
      <button id="btn" @click="alertMe">Clic me please !</button>
    </div>
  </main>

  <RouterView />
</template>

<script>
export default {
  data(){},
  methods: {
    alertMe(){
      alert("Useless alert pop")
    }
  }
}
</script>

<style scoped>
#btn {
  height: 130px;
  width: 130px;
}
</style>
