<template>
  <div class="app">
    <home-page></home-page>
  
  </div>
</template>

<script>
import { computed } from "vue";
import HomePage from './HomePage.vue'

export default {
components: {
  HomePage
},
data() {
  return {
    message: "hello App"
  }
},
// provide一般都是写成函数
provide() {
  return {
    name:"why",
    age:18,
    message:computed(()=> {
      return this.message
    })
  }
}
}
</script>

<style scoped>
</style>