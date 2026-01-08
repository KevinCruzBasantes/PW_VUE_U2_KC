<template>
    <PokemonImagen :pokemonId="101" />
    <PokemonOpciones />
</template>

<script>
    import PokemonImagen from "../components/PokemonImagen.vue"
    import PokemonOpciones from "../components/PokemonOpciones.vue"
export default {
    components:{
        PokemonImagen,
        PokemonOpciones
    }
}
</script>

<style scoped>

</style>