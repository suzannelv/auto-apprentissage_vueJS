<template>
  <div class="info">
    <h2 :class="$attrs.adress">name: {{name}}</h2>
    <h2>age: {{age}}</h2>
    <h2>height: {{height}}</h2>
    <h2>message:{{ showMessage }}</h2>
  </div>
</template>

<script>


export default {
  // 作用：接收父组件传递进来的属性
  // 1. props:数组语法
  // 弊端：1 不能对类型进行验证。2 没有默认值
  // props: ["name", "age", "height"]

  // 2. props对象语法(important)
  // inheritAttrs: false,
  props: {
    name: {
      type: String,
      default: "name par défaut"
    },
    age: {
      type: Number,
      required: true,
      default:0
    },
    height: {
      type: Number,
      default:1.9
    },
    // 原则：对象类型写默认值时，需要编写default的函数，函数返回默认值
    friend: {
      type: Object,
      default: ()=>({name:"james"})
    },
    hobbies: {
      type: Array,
      default: ()=>["basketball", "sing", "rap"]
    },
    showMessage: {
      type: String,
      default:"je suis showMessage"
    }

  }

}
</script>

<style scoped>
</style>