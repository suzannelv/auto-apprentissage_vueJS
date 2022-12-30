<template>
  <div class="app">
    <h2>App message: {{ message }}</h2>
    <home-page></home-page>
    <category-page></category-page>
  </div>
</template>

<script>
import eventBus from './utils/event-bus';
import HomePage from './HomePage.vue';
import CategoryPage from './categoryPage.vue'

export default {
components: {
  HomePage,
  CategoryPage

},
data() {
return {
  message: "hello APP"
}
},

created() {
  // fetch
  // listen event
  eventBus.on("whyevent", (name, age, height)=>{
    console.log("whyevent app", name, age, height)
    this.message=`name:${name}, age:${age}, height:${height}`
  })

}
}
</script>

<style scoped>
</style>