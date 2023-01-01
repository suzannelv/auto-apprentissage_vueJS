<template>
  <div>
    <h2>ShowInfo: {{ info }}</h2>
<!-- 正确做法：要符合单项数据流 -->
    <button @click="showInfoClick">Showinfo bouton</button>
    <hr>
    <!-- 使用readOnly的数据-->
    <h2>showInfo:{{ roInfo }}</h2>
    <!-- 代码会无效(报告警告) -->
    <!-- <button @click="roInfo.name='james'">showinfo</button> -->
    <!-- 正确做法: -->
    <button @click="roInfoBtnClick">roInfo</button>
  </div>
</template>

<script>
export default {
  props:{
        info:{
          type: Object,
          default:()=>({})
        }
  },
  // readOnly
  roInfo:{
    type:Object,
    default:()=>({})
  },

emits: ["changeInfo", "changeRoInfoName"],
setup(props, context){
 function showInfoClick() {
  context.emit("changeInfo", "kobe")
  }

  function roInfoBtnClick() {
    context.emit("changeRoInfoName", "James")
  }

  return {
    showInfoClick,
    roInfoBtnClick
  }
}

}
</script>

<style scoped>
</style>