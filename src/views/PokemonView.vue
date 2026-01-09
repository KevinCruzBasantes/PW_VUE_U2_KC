<template>
    <p>{{ mensaje }}</p>
    <PokemonImagen :pokemonId="pokemonGanador" />
    <PokemonOpciones @seleccionado="evaluarGanador($event)"  :listaPokemon="pokemonArr"/>
</template>

<script>
    import PokemonImagen from "../components/PokemonImagen.vue"
    import PokemonOpciones from "../components/PokemonOpciones.vue"
    import {obtenerVectorPokemonFacade, obtenerAlorioFacade} from "../clients/PokemonClient.js"
    export default {
    components:{
        PokemonImagen,
        PokemonOpciones,

    },
    data(){
        return{
            pokemonArr:[],
            pokemonGanador: null,
            mensaje:null
        }
    },
    mounted(){
        console.log("Componente Montado")
        this.iniciarJuego();
    },
    methods:{
        async iniciarJuego(){
            this.pokemonArr = await obtenerVectorPokemonFacade();
            const aletorioId = obtenerAlorioFacade(0,3)
            this.pokemonGanador = this.pokemonArr[aletorioId].id;
        },
        evaluarGanador(idGanador){
            
            console.log("Valor recibido desde padre")
            console.log(idGanador)
            if(idGanador == this.pokemonGanador){
                console.log("Ganaste")
                this.mensaje="Ganaste"
            }else{
                console.log("Perdiste")
                this.mensaje="Perdiste"
            }
        }

    }
}
</script>

<style scoped>
 p{
    font-size: 40px;
    text-align: center;
 }
</style>