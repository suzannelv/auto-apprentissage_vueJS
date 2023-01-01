<template>
  <h2>{{ fullName }}</h2>
  <h2>{{ scoreLevel }}</h2>
</template>

<script> 
import {reactive, computed, ref} from 'vue'
export default {
  setup(){
    // 1 définit les données
    const names = reactive({
      firstName:"Kobe",
      lastName:"Bryant"
    })
    
    const fullName = computed(()=>{
      return names.firstName + " " + names.lastName
    })
    //  2. definir score
    const score = ref(76)
    const scoreLevel = computed(() =>{
      return score.value >=60? "bien": "bon courage"
    })

    return {
      names,
      fullName,
      scoreLevel
    }
  }
}
</script>

<style scoped>
</style>
