<template>
  <div>
    <h2>home component</h2>
    <h2>compter:{{ counter }}</h2>
    <button @click="counter++">+1</button>
  </div>
</template>

<script>
export default {
  name:"home",
data() {
  return{
    counter:0
  }
},
created(){
  console.log("home create")
},
unmounted() {
  console.log("home unmounted")
},
// 对于保持keep-alive组件监听有没有进行切换
activated() {
  console.log("activated")
},
deactivated() {
  console.log("deactivated")
}
}
</script>

<style scoped>
</style>