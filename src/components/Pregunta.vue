<template>
  <div>
    <img v-if="imagen" :src="imagen" alt="NO SE PUEDE VER LA IMAGEN" />
    <div class="oscuro"></div>
    <div class="pregunta-container">
      <input v-model="pregunta" type="text" placeholder="HAZ UNA PREGUNTA" />
      <p>Recuerda terminar la pregunta con signo de interrogacion (?)</p>
      <h2>{{ pregunta }}</h2>
      <h1>{{ respuesta }}</h1>
    </div>
  </div>
</template>

<script>
//se importa el metodo para consumir la API desde client YesNoClient.js
import { consumirAPIFacade } from "../clients/YesNoClient.js";
export default {
  data() {
    return {
      pregunta: null,
      respuesta: null,
      imagen: null,
    };
  },
  watch: {
    pregunta(value, oldValue) {
      if (value.includes("?")) {
        //llamar a la API
        this.respuesta = "Pensando...";
        this.consumir();
      }
    },
  },
  //se crea un metodo asincronico para consumir la API YA QUE TODO DEBE ESTAR ACORDE PARA NO TENER UNDEFINED
  methods: {
    async consumir() {
      const res = await consumirAPIFacade();
      this.imagen = res.image;
      console.log("Se hizo la pregunta a la API");
      console.log(res);
      console.log(res.answer);
      this.respuesta = res.answer;
    },
  },
};
</script>
  
<style>
img,
oscuro {
  height: 100vh;
  width: 100vw;
  max-height: 100%;
  max-width: 100%;
  position: fixed;
  left: 0px;
  top: 0px;
}
.pregunta-container {
  display: flex;
  position: relative;
  color: white;
  min-height: 100vh; /* altura de toda la pantalla */
  display: flex;
  flex-direction: column; /* elementos uno debajo del otro */
  justify-content: center; /* centrado vertical */
  align-items: center; /* centrado horizontal */
  font-size: 60px;
}
input {
  font-size: 50px;
  text-align: center;
  border-radius: 10px;
  padding: 10px;
  border: none;
}
input:focus {
  outline: none;
}
.oscuro {
  background-color: rgba(0, 0, 0, 0.4);
}
</style>