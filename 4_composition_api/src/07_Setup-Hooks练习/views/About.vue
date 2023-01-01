<template>
  <div>
    <h2>About</h2>
    <h2>counter:{{ counter }}</h2>
  <button @click="increment">+1</button>
  <button @click="decrement">-1</button>
  </div>
</template>

<script>
import useCounter from '../hooks/useCounter';
import useTitle from '../hooks/useTitle'

export default {
setup(){

  // toggle titre
  useTitle("about")
  return{
    ...useCounter()
  }
}
}
</script>

<style scoped>
</style>