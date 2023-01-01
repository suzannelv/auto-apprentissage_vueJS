<template>
  <div><h2>Home</h2></div>
  <h2>counter:{{ counter }}</h2>
  <button @click="increment">+1</button>
  <button @click="decrement">-1</button>


  <button @click="popularClick">home-popular</button>
  <button @click="hotClick">home-hot</button>
  <button @click="listClick">home-list</button>

</template>

<script>
import useCounter from '../hooks/useCounter';
import useTitle from "../hooks/useTitle";
export default {
  setup() {
    const {counter, increment, decrement}=useCounter()
    // toggle page
    const title = useTitle("accueil")

    // écouter les clicks de boutons
    function popularClick() {
      title.value = "accueil-popular"
    }
    function hotClick() {
      title.value = "accueil-hot"
    } 
    function listClick() {
      title.value = "accueil-list"
    }


    return {
      counter,
      increment,
      decrement,
      popularClick,
      hotClick,
      listClick

      
    }

  }

}
</script>

<style scoped>
</style>