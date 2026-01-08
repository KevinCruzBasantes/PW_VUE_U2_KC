<template>
  <div>
      <!--<ContadorView/>-->
      <!-- <DirectivasView/> -->
      <!--<PreguntaView/>-->
      <PokemonView/>
   </div>
</template>

<script>
import ContadorView from '../src/views/ContadorView.vue';
import DirectivasView from '../src/views/DirectivasView.vue';
import PreguntaView from '../src/views/PreguntaView.vue';
import PokemonView from "../src/views/PokemonView.vue";
export default {
  components:{
    ContadorView,
    DirectivasView,
    PreguntaView,
    PokemonView
  },
}
</script>

<style>

</style>
