<template>
  <div class="app">
    <!-- 1. tab-control -->
<tab-control :titles="['vêtement', 'chaussures', 'pantalon']"
              @tab-item-click="tabItemClick"/>
    <!-- 2. content-->
    <h2>{{ pageContent[currentIndex] }}</h2>
  </div>
</template>

<script>
import TabControl from './TabControl.vue';
export default {
components: {
  TabControl
},
data() {
   return {
   pageContent: ["lite vetement", "liste chaussure", "liste pantalon"],
   currentIndex:0
   }
},
methods: {
  tabItemClick(index) {
    console.log("app:", index)
    this.currentIndex = index
  }

}
}
</script>

<style scoped>
</style>