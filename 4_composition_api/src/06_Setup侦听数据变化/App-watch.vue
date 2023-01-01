<template>
  <div>AppContent</div>
  <button @click="message='bonjour vue'">modifier message</button>
  <button @click="info.friend.name='james'">modifier info</button>
  
  </template>

<script>
import { ref, watch, reactive } from "vue";
export default {
setup() {
  // 1.définir les données
  const message = ref("hello world")
  const info = reactive({
    name:"why",
    age:18,
    friend:{
      name:"kobe"
    }
  })

  // 2. 侦听数据变量
  watch(message, (newValue, oldValue)=>{
   console.log(newValue, oldValue)
  })
  watch(info,(newValue, oldValue)=>{
   console.log(newValue, oldValue)
   console.log(newValue === oldValue)
  },{
    immediate:true
  })
// 3. 监听reactive数据变化后，获取普通对象
watch(()=>({ ...info }), (newValue, oldValue)=> {
  console.log(newValue, oldValue)
},{
  immediate: true,
  deep:true
})
  return {
    message,
    info
  }
}
}
</script>

<style scoped>
</style>