<template>
  <div>message:{{ message }}</div>
  <button @click="message='hello Vincent'">modifier</button>
</template>

<script>
export default {
  data() {
return {
  message:"hello app"
}
  },
  // 1.组件被创建之前
  beforeCreate() {
console.log("beforecreate")
  },
  // 2.组件被创建完成
created() {
console.log("组件被创建完成")
console.log("1 发送网络请求，请求数据")
console.log("2 监听eventbus时间")
console.log("3 监听watch数据")

},

// 3 组件template准备被挂载
beforeMount(){
  console.log("beforemount")
},
// 4 组件template被挂载，虚拟真实
mounted() {
  console.log("mounted")
  console.log("1.获取DOM")
  console.log("2.使用DOM")
},
// 5. 数据发生改变
// 5.1 准备更新DOM
beforeUpdate() {
  console.log("beforeUpdate")
},
// 5.2 更新DOM
updated() {
  console.log("update")
},
// 6. 卸载vnode ->DOM 元素
// 6.1 卸载之前
beforeUnmount() {
  console.log("beforeunmounted")
},
// 6.2 DOM元素卸载完成
unmounted() {
  console.log("unmounted")
}




}
</script>

<style scoped>
</style>