<template>
  <div class="app">
    <div class="tabs">
      <template v-for="item in tabs" :key="item">
        <button :class="{active: currentTab === item }"
                @click="itemClick(item)">{{ item }}</button>
      </template>
    </div>

    <div class="views">

      <!-- 1.v-if -->
      <!-- <template v-if="currentIndex === 0">
        <home-page></home-page>  
      </template>

      <template v-else-if="currentIndex === 1">
       <about-page></about-page>
      </template>

      <template v-else-if="currentIndex===2">
      <category-page></category-page>
      </template> -->


      <!-- 2. 动态组件component -->
      <!--  is中的组件需要两个地方：1，全局注册的组件，2，局部注册的组件-->
      <component :is="currentTab"></component>
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