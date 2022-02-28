<template>
  <div id="app">

    <mostrar-datos/>
  
  </div>
  
</template>

<script>
import MostrarDatos from './components/MostrarDatos.vue'

export default {
  name: 'App',
  components: {
    MostrarDatos
  }
}
</script>

<style>
  #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #428ad1;

  background-image: url('./assets/fondo.jpg');
  min-height: 100vh;
  background-repeat: no-repeat;
  background-size: 100%;
  background-position: center;
  
  
  
  
}

  #navbar{
  margin-left: 10px;
  margin-right: 10px;
  }

</style>
