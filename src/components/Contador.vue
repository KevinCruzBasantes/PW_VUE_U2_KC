<template>
  <div>
    <h1>{{ tit }}</h1>
    <p>{{ numero }} <sup>2</sup>={{ obtenerCuadrado() }}</p>
    <p>{{ numero }} <sup>2</sup>={{ obtenerCuadrado() }}</p>
    <p>{{ numero }} <sup>2</sup>={{ obtenerCuadrado() }}</p>
    <p>{{ numero }} <sup>2</sup>={{ calculaCuadrado }}</p>
    <p>{{ numero }} <sup>3</sup>={{ obtenerCubo() }}</p>
    <p>{{ numero }} <sup>3</sup>={{ calcularCubo }}</p>
  </div>
  <div>
    <button @:click="incrementar()">+1</button>
    <button v-on:click="decrementar()">-1</button>
    <button v-show="mostrar">PRUEBA</button>
  </div>
</template>

<script>
export default {
  //data es la opcion de openapi
  //son como variables del componente reactivamente actualiza la pagina
  data() {
    return {
      numero: this.inicio,
      titulo: "Mi Contador",
    };
  },
  //optionapi para metodos
  methods: {
    obtenerCuadrado() {
      console.log("Entro a obtener cuadrado");
      return this.numero * this.numero;
    },
    obtenerCubo() {
      return this.numero * this.numero * this.numero;
    },
    incrementar() {
      console.log(this.tit);
      this.numero++;
    },
    decrementar() {
      this.numero--;
    },
  },
  //si no hay cambio en el cuerpo en este caso numero no hay respuesta por tanto no cambia
  computed: {
    calculaCuadrado() {
      console.log("Entro a propiedad computada");
      return this.numero * this.numero;
    },
    calcularCubo() {
      return this.numero * this.numero * this.numero;
    },
  },
  //variables que yo puedo instanciar y darles otro valor de otro componenete
  //Declaracion basica de props
  //props: ["tit", "inicio", "mostrar"],
  props: {
    tit: String,
    inicio: {
      type: Number,
      default: 99,
      validator(value){
        return value>10;
      }
    },
    mostrar: Boolean,
  },
  //tipos dato props Number, Boolean, Array, Date, Funciones, Object, BigInt
};
</script>

<style>
</style> 