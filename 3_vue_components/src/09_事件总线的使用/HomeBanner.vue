<template>
  <div class="banner">
    <button @click="bannerBtnClick">Banner bouton</button>
  </div>
</template>

<script>
import eventBus from './utils/event-bus'
export default {
methods: {
  bannerBtnClick() {
    console.log("banner")
    eventBus.emit("whyevent", "why", 18, 1.99)
  }
}
}
</script>

<style scoped>
</style>