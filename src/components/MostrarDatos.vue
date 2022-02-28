<template>
  <div>
    <div class="row">
    <div class="row">
    <div class="col m12 card blue-grey darken-4">

      <form @submit.prevent="agregarUsuario">
          <div class="row">
            <div class="col m4">
              <label class="white-text text-darken-2">Nombre <b-icon icon="file-person"></b-icon></label>
              <input type="text" v-model="nombre" class="white-text text-darken-2">
            </div>
            <div class="col m4">
              <label class="white-text text-darken-2">Apellido <b-icon icon="file-person"></b-icon></label>
              <input type="text" v-model="apellido" class="white-text text-darken-2">
            </div>
          </div>

        <div class="row">
          <div class="col m4">
            <label class="white-text text-darken-2">DUI <b-icon icon="card-heading"></b-icon></label>
            <input type="text" v-model="DUI" class="white-text text-darken-2">
          </div>
         
          <div class="col m4">
            <label class="white-text text-darken-2">Modelo de carro <b-icon icon="truck"></b-icon></label>
          <input type="text" v-model="modelodecarro" class="white-text text-darken-2">
          </div>
        </div>
        
          <div class="col m4">
            <label class="white-text text-darken-2">Precio <b-icon icon="cart"></b-icon></label>
            <input type="text" v-model="precio" class="white-text text-darken-2">
        </div>
        <br>
        <br>
        <br>
        <br>
        
        <div class="row">
          <button type="submit" class="btn purple darken-4">Agregar usuario <b-icon icon="archive-fill"></b-icon></button>
        </div>
      </form> 
    </div>
  </div>

  <div class="row">
    <div class="col m12">
      <table class="table bordered striped black white-text text-darken-2 ">
        <thead>
          <tr>
            <th>Nombre <b-icon icon="file-person"></b-icon></th>
            <th>Apellido <b-icon icon="file-person"></b-icon></th><br>
            <th>DUI <b-icon icon="card-heading"></b-icon></th><br>
            <th>Modelo de Carro <b-icon icon="truck"></b-icon></th>
            <th>Precio <b-icon icon="cart"></b-icon></th>
          </tr>
        </thead>
        <tbody>
            <tr v-for="usuario in usuarios" v-bind:key="usuario">
              <td>{{usuario.nombre}}</td>
              <td>{{usuario.apellido}}</td><br>
              <td>{{usuario.DUI}}</td><br>
              <td>{{usuario.modelodecarro}}</td>
              <td>{{usuario.precio}}</td>
            </tr>
        </tbody>
      </table>
    </div>
  </div>
  </div>

  </div>
  
</template>


<script>
import M from "materialize-css"
export default {
    name: "MostrarDatos",
    data(){
    return {
      nombre: '',
      apellido: '',
      edad: 0,
      DUI: '',
      modelodecarro: '',
      precio: 0,
      usuarios: [],

      select_instances: []
    }
  },
  mounted()
  {
    var elems = document.querySelectorAll('select');
    this.select_instances = M.FormSelect.init(elems, null);
  },
  methods: {
    agregarUsuario()
    {
      var data = {
        nombre: this.nombre,
        apellido: this.apellido,
        edad: this.edad,
        modelodecarro: this.modelodecarro,
        DUI: this.DUI,
        precio: this.precio
      };
      this.usuarios.push(data);
      this.nombre = '';
      this.apellido = '';
      this.DUI = 0;
      this.modelodecarro = '';
      this.precio = 0;
    },
  }

}


</script>

<style>

</style>