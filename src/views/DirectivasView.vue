<template>
  <div class="view-container">
    <h2>PRUEBA</h2>
    <Directivas/>
    
  </div>
</template>

<script>
import Directivas from "../components/Directivas.vue";
export default {
    components:{
        Directivas,
    },
}
</script>

<style>
.view-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
h2{
  font-size: 50px;
}
</style>
