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
    <br />
    <label for="id_nombre1">Nombre: </label>
    <input v-model="nombre" v-on:keypress="agregarEstudiantes1" type="text" id="id_nombre1" />
    <label for="id_apellido1">Apellido: </label>
    <input
      v-model="apellido"
      v-on:keypress.enter="agregarEstudiantes1"
      type="text"
      id="id_apellido1"
    />
    <br />
    <ul>
      <li
        v-show="nombre !== null"
        v-for="{ nombre, apellido } in arreglo"
        :key="nombre"
      >
        {{ nombre }}-{{ apellido }}
      </li>
    </ul>
    <h2>TABLA</h2>
    <table style="border: 5px solid blue">
      <tr>
        <th>Nombre</th>
        <th>Apellido</th>
      </tr>
      <tr v-for="{ nombre, apellido } in arreglo" :key="nombre">
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
    agregarEstudiante(event) {
      const estu = {
        nombre: this.nombre,
        apellido: this.apellido,
      };
      if (event.charCode != 13) {
        return;
      }
      console.log("Agregar estudiante");
      console.log(estu);
      this.arreglo.push(estu);
      this.limpiar();
    },
    limpiar() {
      this.nombre = "";
      this.apellido = "";
    },
    agregarEstudiantes1(event) {
      console.log("evento");
      const estu2 = {
        nombre: this.nombre,
        apellido: this.apellido,
      };
      if (event.charCode != 13) {
        return;
      }

      console.log("Presiono ENTER ");
      console.log("Agregar estudiante 1");
      console.log(event);
      console.log(event.charCode);
      console.log("Agregar estudiante");
      console.log(estu2);
      this.arreglo.push(estu2);
      this.limpiar();
    },
    agregarEstudianteEnter(event) {
      if (event.charCode != 13) {
        return;
      }
      const estu = {
        nombre: this.nombre,
        apellido: this.apellido,
      };
      console.log("Agregar estudiante");
      console.log(estu);
      this.arreglo.push(estu);
      this.limpiar();
    },
  },
};
</script>

<style>
</style>