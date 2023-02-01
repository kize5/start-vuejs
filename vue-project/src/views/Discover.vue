<template>
  <div id="container"></div>
  <h1 :class="{ red: isActive }">h1{{ titre }}</h1>
  <input v-model="textInput" type="text">
  <h2 :class="{ red: isActive }">Je suis un h2</h2>
  <button @click="newTitle">Clic me</button>
  <br>
  <div id="check-container">
    <input type="checkbox" id="check1" @change="isActive = !isActive">
    <input type="checkbox" id="check2" @change="showImg">
<!--    <input type="checkbox" id="check2" v-model="isActive">-->
  </div>
  <div v-if="srcImg !== ''" id="imgdiv">
  <img :src="srcImg" alt="fuck this shit !">
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
      titre: "",
      textInput: "",
      srcImg: "",
      url:"https://mixmag.fr/assets/uploads/images/_columns2/ghibli-2020-Cropped.jpg"
    }
  },
  methods: {
    newTitle() {
      this.titre = this.textInput
    },
    showImg() {
      if (this.srcImg === "") {
        return this.srcImg = "https://mixmag.fr/assets/uploads/images/_columns2/ghibli-2020-Cropped.jpg"
    } else return this.srcImg = ""
    // return this.srcImg = "" ? this.srcImg = this.url : this.srcImg=""
    }
  }
}
</script>

<style scoped>
#check-container {
  display: flex;
  flex-direction: column;
  margin: 20px;
}
#check-container input {
  margin: 10px;
  height: 20px;
}
.red {
  color: red;
}
</style>