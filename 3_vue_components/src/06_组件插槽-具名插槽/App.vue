<template>
  <nav-bar>
    <template #left>
      <button>></button>
    </template>
    <template v-slot:center>
      <span>content</span>
    </template>
    <template v-slot:right>
      <a href="#">Sign In</a>
    </template>
  </nav-bar>
  <!-- 动态插入数据 -->
  <nav-bar>
    <template v-slot:[position]>
      <a href="#">register</a>
    </template>
  </nav-bar>
    <button @click="position='left'">left</button>
    <button @click="position='center'">center</button>
    <button @click="position='right'">right</button>

 
</template>

<script>
import NavBar from './NavBar.vue';
export default {
components: {
  NavBar
},
data() {
  return {
    position:"center"
  }
}
}
</script>

<style scoped>
</style>