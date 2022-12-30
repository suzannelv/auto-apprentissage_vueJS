<template>
  <div class="app">
    <!-- buton -->
     <show-message title="kiki">
      <button>Buton</button>
     </show-message>
    <!--a href  -->
     <show-message>
      <a href="#">google</a>
     </show-message>
    <!-- img -->
     <show-message >
      <img src="@/img/chat.jpg" alt="">
     </show-message>

     <!-- pas de contenu dans le slot -->
     <show-message></show-message>
  </div>
 
</template>

<script>
import ShowMessage from './ShowMessage.vue';
export default {
components:{
ShowMessage
}
}
</script>

<style scoped>

img{
  width: 100px;
  height: 100px;
}
</style>