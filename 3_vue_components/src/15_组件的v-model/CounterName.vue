<template>
  <div>counter:{{counter}}</div>
  <button @click="changerCounter">changer counter</button>
</template>

<script>
export default {
props:{
  counter:{
    type:Number,
    default:0
  },
 emits:["update:counter"],
  methods:{
    changerCounter() {
     this.$emit("update:counter", 999)
    }
  }

}
}
</script>

<style scoped>
</style>