<template>
  <div>
    <h2>app:{{ info }}</h2>
    <show-info :info="info" :roInfo="roInfo" @changeInfo="changeInfo" @changeRoInfoName="changeRoInfoName"></show-info>
  </div>
</template>

<script>
import {reactive, readonly} from 'vue'
import ShowInfo from './ShowInfo.vue'
export default {
components:{
  ShowInfo
},
setup() {
  // 本地定义做个数据，都需要传递给子组件
  //name/age/height
  const info = reactive({
    name:"why",
    age:18,
    height:1.88
  }) 

  function changeInfo(payload) {
    info.name = payload
  }

  // 使用readOnly包裹info
  const roInfo = readonly(info)
  function changeRoInfoName(payload){
    info.name = payload
  }

  return {
    info,
    changeInfo,
    roInfo,
    changeRoInfoName


  }

}
}
</script>

<style scoped>
</style>