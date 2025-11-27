<template>
  <div>
    <Contador tit="Contador1" :inicio="4+4" :mostrar="true"/>
    <Contador tit="Contador2"  :inicio="20" :mostrar="false"/>

  </div>
</template>

<script>
import Contador from '../components/Contador.vue'
export default {
    components:{
        Contador,
    },
}
</script>

<style>

</style>