<template>
  <div>
    <label for="">Nombre</label>
    <input v-model="nombre" id="id_nombre" type="text" />
    <p>{{ nombre }}</p>

    <label for="">Apellido</label>
    <input v-model="apellido" id="id_apellido" type="text" />
    <p>{{ apellido }}</p>
    <button v-on:click="imprimirNombre()">Imprimir Nombre</button>
    <button v-on:click="agregarEstudiante()">Agregar Estudiante</button>
    <h1>{{ arreglo }}</h1>
    <ul>
      <li  v-show="nombre!==null" 
      v-for="{ nombre, apellido} in arreglo" :key="nombre">
        {{nombre }}-{{apellido }}</li>
    </ul>
    <h2>TABLA</h2>
    <table style="border: 5px solid blue;">
        <tr >
            <th>Nombre</th>
            <th>Apellido</th>
        </tr>
        <tr v-for="{ nombre, apellido} in arreglo" :key="nombre">
            <td>{{ nombre }}</td>
            <td>{{ apellido }}</td>
        </tr>
    </table>

  </div>
</template>

<script>
export default {
  data() {
    return {
      nombre: null,
      apellido: null,
      arreglo: [],
    };
  },
  methods: {
    imprimirNombre() {
      console.log(this.nombre);
    },
    agregarEstudiante() {
      const estu = {
        nombre: this.nombre,
        apellido: this.apellido,
      };
      console.log("Agregar estudiante");
      console.log(estu);
      this.arreglo.push(estu);
      this.limpiar();
    },
    limpiar() {
      this.nombre = "";
      this.apellido = "";
    },
  },
};
</script>

<style>
</style>