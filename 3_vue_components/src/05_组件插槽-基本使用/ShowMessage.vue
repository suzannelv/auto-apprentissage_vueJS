<template>
  <h2>{{title}}</h2>
  <div class="content">
    <slot>je suis slot</slot>
  </div>
</template>

<script>
export default {
props:{
  title:{
    type:String,
    default:"je suis titre par défault"
  },
  content:{
    type: String,
    default:""
  }
}
}
</script>

<style scoped>
</style>