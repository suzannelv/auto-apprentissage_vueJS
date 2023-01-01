<template>
  <div>
    <h2>message: {{ message }}</h2>
    <button @click="changeMessage">modifier</button>
  <hr>
  <h2>compte: {{ account.username }}</h2>
  <h2>mot de pass: {{ account.password }}</h2>
  <button @click="changeAccount">modifier le compte</button>

  <hr>
   <!--默认情况下在template中使用ref时，Vue会自动对其进行解包，取出其中的value  -->
  <h2>当前计数:{{ counter }}</h2>
  <button @click="increment">+1</button>
<hr>
  <!-- 使用时不需要写.value -->
  <h2>当前计数:{{ info.counter }}</h2>
  <!-- 修改的时候需要写.value -->
  <button @click="info.counter.value++">+1</button>
  </div>

</template>

<script>
import {reactive, ref} from 'vue';

export default {
setup() {
  // 1 定义普通的数据：可以正常的被使用，但是数据不是响应式的
 let message="hello composition API"

//  2 定义响应式数据
// 2.1 reactive函数：定义复杂类型的数据
const account = reactive({
  username:"why",
  password:"123456"
}) 

function changeAccount() {
  account.username="kobe"
}

// 2.2 ref函数：定义简单类型的数据，也可以定义复杂类型的数据
// counter定义响应式数据
const counter = ref(0)
function increment() {
  counter.value++
}

// 3 ref是浅层解包
const info={
  counter
}

function changeMessage(){
  message = "bonjour vue"
  console.log(message)
}


  return {
    message,
    changeMessage,
    account,
    changeAccount,
    counter,
    increment,
    info
  }
}
}
</script>

<style scoped>
</style>