<template>
  <div>
    <h2>compter:{{ counter }}</h2>
    <button @click="counter++">+1</button>
  </div>
</template>

<script>
import {watchEffet, ref} from 'vue'
export default {
setup() {
  const counter=ref(0)
// 1.watchEffet
  watchEffet(()=>{
    console.log("---", counter.value)
  })
  return {
    counter
  }
}
}
</script>

<style scoped>
</style>