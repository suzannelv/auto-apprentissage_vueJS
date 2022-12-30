<template>
  <div>counter:{{modelValue}}</div>
  <button @click="changerCounter">changer counter</button>
</template>

<script>
export default {
props:{
  modelValue:{
    type:Number,
    default:0
  },
  emits:["update:modelValue"],
  methods:{
    changerCounter() {
     this.$emit("update:modelValue", 999)
    }
  }

}
}
</script>

<style scoped>
</style>