<template>
  <div id="app">
    <b-button v-b-toggle.sidebar-right class="grey darken-4">INTEGRANTES</b-button>
    <b-sidebar id="sidebar-right" title="Parcial #1" right shadow >
      <div class="px-3 py-2">
        <h4>INTEGRANTES</h4>
        <p>Mauricio Enmanuel Montiel Ruiz - SMIS952220</p>
        <p>Jose Rodolfo Vasquez Bonilla - SMIS037117</p>
        <br><br>
        <p>
        NOTA: 
        Este parcial solo se hizo entre 2 personas.
        </p>
      </div>
    </b-sidebar>
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
