<template>
  <div class="app">
    <input v-model="message">


<!--组件的 v-model：默认modelValue -->
<!-- <counter-page v-model="appCounter"></counter-page> -->
<!-- 相当于 -->
<!-- <counter-page v-bind:modelValue="appCounter"  @update:modelValue="appCounter = $event"></counter-page> -->

<!-- 组件的 v-model：自定义名称 counter-->
<counter-name v-model:counter="appCounter"></counter-name>

  </div>
</template>

<script>
import CounterPage from "./CounterPage.vue";
import CounterName from "./CounterName.vue";
export default {
  components:{
    CounterPage,
    CounterName
  },
 data() {
  return {
    message:"hello vue",
    appCounter:100
  }
 }
}
</script>

<style scoped>
</style>