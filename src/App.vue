<template>
  <div id="app">
    <div id="navbar">
    <b-navbar toggleable="lg" type="dark" variant="dark" >
    <b-navbar-brand href="#">Pagina Principal <b-icon icon="house" ></b-icon></b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item href="#" icon="trash">Insertar registros <b-icon icon="archive-fill" ></b-icon></b-nav-item>
        <b-nav-item href="#">Borrar registros <b-icon icon="trash-fill"></b-icon></b-nav-item>
        <b-nav-item href="#">Modificar registros  <b-icon icon="arrow-clockwise" animation="spin"></b-icon></b-nav-item>
        
      
      </b-navbar-nav>

     
    </b-collapse>
  </b-navbar>

  
  </div>
  
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
