<template>
  <div>
    <img
      src="https://yesno.wtf/assets/yes/1-af11222d8d4af90bdab8fc447c8cfebf.gif"
      alt="NO SE PUEDE VER LA IMAGEN"
    />
    <div class="pregunta-container">
      <input type="text" placeholder="HAZ UNA PREGUNTA" />
      <p>Recuerda terminar la pregunta con signo de interrogacion (?)</p>
      <h2>Sere millonario?</h2>
      <h1>Yes, No</h1>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
img {
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
</style>