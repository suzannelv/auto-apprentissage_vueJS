<template>
  <div class="app">
    <div class="tabs">
      <template v-for="item in tabs" :key="item">
        <button :class="{active: currentTab === item }"
                @click="itemClick(item)">{{ item }}</button>
      </template>
    </div>

    <div class="views">
      <keep-alive include="home,about">
        <component :is="currentTab"></component>
      </keep-alive>
      
    </div>

  </div>
</template>

<script>
import HomePage from './views/HomePage.vue'
import AboutPage from './views/AboutPage.vue'
import CategoryPage from './views/CategoryPage.vue'


export default {
  components:{
    HomePage,
    AboutPage,
    CategoryPage
  },

data() {
  return{
    tabs:["HomePage", "AboutPage", "CategoryPage"],
    // currentIndex:0
    currentTab:"HomePage"
  }
},
methods:{
  itemClick(item) {
this.currentTab = item
  }
}
}
</script>

<style scoped>
.active{
  color: red;
}
</style>