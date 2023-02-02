<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>
<template>

  <ul class="background">
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
  </ul>

  <header>
    <div class="wrapper">
      <nav>
        <router-link to="/" class="nav-link">Home</router-link>
        <router-link to="/villes" class="nav-link">Villes</router-link>
        <router-link to="/ville" class="nav-link">Ville</router-link>
      </nav>
    </div>
  </header>


  <main>
    <div class="container">
      <RouterView />
      <div id="btn-div">
      <button id="btn" @click="alertMe">Clic me please !</button>
      </div>
      </div>
  </main>


</template>

<script>
export default {
  // data(){},
  methods: {
    alertMe(){
      alert("Useless alert pop")
    }
  }
}
</script>

<style scoped>


.nav-link {
  margin: 20px;
}

#btn {
  height: 75px;
  width: 75px;
}

@keyframes cube {
  from {
    transform: scale(0) rotate(0deg) translate(-50%, -50%);
    opacity: 1;
  }
  to {
    transform: scale(20) rotate(960deg) translate(-50%, -50%);
    opacity: 0;
  }
}

.background {
  position: fixed;
  width: 100vw;
  height: 100vh;
  top: 0;
  left: 0;
  margin: 0;
  padding: 0;
  background: #0040C1;
  overflow: hidden;
}
.background li {
  position: absolute;
  top: 80vh;
  left: 45vw;
  width: 10px;
  height: 10px;
  border: solid 1px #0039ad;
  color: transparent;
  transform-origin: top left;
  transform: scale(0) rotate(0deg) translate(-50%, -50%);
  animation: cube 7s ease-in forwards infinite;
}

.background li:nth-child(0) {
  animation-delay: 0s;
  left: 27vw;
  top: 70vh;
}

.background li:nth-child(1) {
  animation-delay: 2s;
  left: 41vw;
  top: 20vh;
}

.background li:nth-child(2) {
  animation-delay: 4s;
  left: 74vw;
  top: 95vh;
}

.background li:nth-child(3) {
  animation-delay: 6s;
  left: 93vw;
  top: 42vh;
}

.background li:nth-child(4) {
  animation-delay: 8s;
  left: 87vw;
  top: 6vh;
}

.background li:nth-child(5) {
  animation-delay: 10s;
  left: 22vw;
  top: 47vh;
  border-color: #0046d4;
}

.background li:nth-child(6) {
  animation-delay: 12s;
  left: 55vw;
  top: 80vh;
}

.background li:nth-child(7) {
  animation-delay: 14s;
  left: 7vw;
  top: 14vh;
}

.background li:nth-child(8) {
  animation-delay: 16s;
  left: 62vw;
  top: 39vh;
  border-color: #0046d4;
}

.background li:nth-child(9) {
  animation-delay: 18s;
  left: 65vw;
  top: 2vh;
}

.background li:nth-child(10) {
  animation-delay: 20s;
  left: 5vw;
  top: 26vh;
}

.background li:nth-child(11) {
  animation-delay: 22s;
  left: 34vw;
  top: 43vh;
  border-color: #0046d4;
}

.background li:nth-child(12) {
  animation-delay: 24s;
  left: 57vw;
  top: 52vh;
  border-color: #0046d4;
}

.background li:nth-child(13) {
  animation-delay: 26s;
  left: 92vw;
  top: 54vh;
  border-color: #0046d4;
}

.background li:nth-child(14) {
  animation-delay: 28s;
  left: 19vw;
  top: 75vh;
  border-color: #0046d4;
}

.background li:nth-child(15) {
  animation-delay: 30s;
  left: 30vw;
  top: 65vh;
}

.background li:nth-child(16) {
  animation-delay: 32s;
  left: 12vw;
  top: 99vh;
  border-color: #0046d4;
}

.background li:nth-child(17) {
  animation-delay: 34s;
  left: 3vw;
  top: 57vh;
  border-color: #0046d4;
}

.background li:nth-child(18) {
  animation-delay: 36s;
  left: 48vw;
  top: 87vh;
  border-color: #0046d4;
}

.background li:nth-child(19) {
  animation-delay: 38s;
  left: 77vw;
  top: 73vh;
  border-color: #0046d4;
}

.background li:nth-child(20) {
  animation-delay: 40s;
  left: 70vw;
  top: 33vh;
  border-color: #0046d4;
}

.background li:nth-child(21) {
  animation-delay: 42s;
  left: 46vw;
  top: 91vh;
  border-color: #0046d4;
}

.background li:nth-child(22) {
  animation-delay: 44s;
  left: 82vw;
  top: 63vh;
  border-color: #0046d4;
}

.background li:nth-child(23) {
  animation-delay: 46s;
  left: 51vw;
  top: 23vh;
  border-color: #0046d4;
}

.background li:nth-child(24) {
  animation-delay: 48s;
  left: 79vw;
  top: 31vh;
  border-color: #0046d4;
}

.background li:nth-child(25) {
  animation-delay: 50s;
  left: 98vw;
  top: 11vh;
}

.background li:nth-child(26) {
  animation-delay: 52s;
  left: 38vw;
  top: 10vh;
  border-color: #0046d4;
}

.background li:nth-child(27) {
  animation-delay: 54s;
  left: 16vw;
  top: 83vh;
}

</style>
