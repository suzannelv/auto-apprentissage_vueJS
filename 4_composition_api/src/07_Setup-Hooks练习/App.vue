<template>
  <div>AppContent</div>

  <button @click="changeTitle">change title</button>
  <home></home>
  <hr>
  <about></about>

  <!-- home/about toggle page -->
  <button @click="currentPage = 'home'">home</button>
  <button @click="currentPage = 'about'">About</button>

  <component :is="currentPage"></component>
</template>

<script>
import {ref} from 'vue';
import Home from "./views/Home.vue";
import About from "./views/About.vue";
import useTitle from './hooks/useTitle'

export default {
  components:{
    Home,
    About,

},
setup() {
  const currentPage=ref("home")
  function changeTitle(){
   useTitle("app title")
  }

  return {
    changeTitle,
    currentPage
  }
}

}
</script>

<style scoped>
</style>