<template>
<div class="app">
 component app
 <!-- template中的 ref对象会自动解包 -->
 <h2>compter{{ counter }}</h2>
 <button @click="increment">+1</button>
 <button @click="decrement">-1</button>
</div>
</template>

<script>
// import {ref} from 'vue'
import useCounter from '../hooks/useCounter'

export default {
  setup() {
    // 1.定义counter的内容
    // 默认定义的数据都不是响应的数据
    // let counter=ref(0)
    // const increment=()=>{
    
    //   counter.value++
    // }
    // const decrement=()=>{
  
    //   counter.value--
    // }


// const {counter, increment, decrement} = useCounter()
//     return {
//       counter,
//       increment, 
//       decrement
//     }

return {
  ...useCounter()
}

  }
}
</script>

<style>

</style>
