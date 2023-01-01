<template>
  <!-- 1.obtenir les éléments -->
  <h2 ref="titleRef">Titre</h2>
  <button ref="btnRef">bouton</button>
  <button @click="getElement">get element</button>
<!-- 2.获取组件实例 -->
<show-info ref="showInfoRef"></show-info>
</template>

<script>
import ShowInfo from './ShowInfo.vue'
import {ref, onMounted} from 'vue'

export default {
  components:{
    ShowInfo
  },
setup() {
  const titleRef = ref()
  const btnRef = ref()
  const showInfoRef=ref()

  // onMounted 生命周期函数
  onMounted(()=>{
    console.log(titleRef.value)
    console.log(btnRef.value)
    console.log(showInfoRef.value)

    showInfoRef.value.showInfoFoo()
  }) 

  function getElement() {
    console.log(titleRef.value)
  }

  return {
    titleRef,
    btnRef,
    showInfoRef,
    getElement
  }
}
}
</script>

<style scoped>
</style>