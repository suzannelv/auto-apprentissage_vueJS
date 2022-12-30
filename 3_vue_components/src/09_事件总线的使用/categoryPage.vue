<template>
  <div>
    <h2>category</h2>
  </div>
</template>

<script>
import eventBus from './utils/event-bus';
export default {
  methods: {
    whyEventHandler() {
      console.log("lisen in category")
    }
  },
 created(){
  eventBus.on("whyevent",this.whyEventHandler)
 },
 unmounted() {
  console.log("category unmounted")
  eventBus.off("whyevent", this.whyEventHandler)
 }

}
</script>

<style scoped>
</style>