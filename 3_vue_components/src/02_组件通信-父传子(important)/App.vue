<template>
  <!-- 1.montrer les infos why -->
  <!-- 如果当前的属性是一个非props的attribute，那么该属性会默认添加到子组件的根元素上 -->
  <show-info name="why" age="18" height="1.88"
             adress="lyon" class="active"/>

<!-- 2.montrer les infos kobe -->
  <show-info name="kobe" age="20" height="1.89"/>

  <ShowInfo age="28" show-message="kiki"/>

</template>

<script>
import ShowInfo from './ShowInfo.vue';
export default {
components:{
  ShowInfo
}
}
</script>

<style scoped>
</style>