<template>
  <div class="app">
     <h2 ref="title" class="title" :style="{color:titleColor}">{{message}}</h2>
     <button ref="btn" @click="changeTitle">modifier</button>
     <banner-page ref="banner"></banner-page>
  </div>
</template>

<script>
import BannerPage from './BannerPage.vue'
export default {
  components: {
    BannerPage
  },
 data() {
  return {
    message: "helle App",
    titleColor: "red"
  }
 },
 methods: {
  changeTitle() {
    // this.message="bonjour Vue",
    // this.titleColor="blue"

    // 1. obtenir h2/button element
    console.log(this.$refs.title)
    console.log(this.$refs.btn)
    // 2. 获取banner组件：组件实例
    console.log(this.$refs.banner)

    // 2.1 在父组件中可以主动调用子组件的对象方法
    this.$refs.banner.bannerClick()
    // 2.2 获取banner组件实例，获取banner中的元素
   console.log(this.$refs.banner.$el)
  //  2.3 如果banner中的template是多个根，拿到的是第一个node节点
  // 注意：开发中不推荐一个组件的template中有多个根元素
  console.log(this.$refs.banner.$el.nextElementSibling

  )
 }

}
}
</script>

<style scoped>
</style>