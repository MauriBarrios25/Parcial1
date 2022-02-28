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
          <button type="submit" class="btn purple darken-4">{{(indice == -1 ? 'Agregar':'actualizar')}} <b-icon icon="archive-fill"></b-icon></button>
        </div>
      </form> 
    </div>
  </div>

  <div class="row">
    <div class="col m12">
      <table class="table bordered striped grey darken-4 white-text text-darken-2 ">
        <thead>
          <tr>
            <th>Nombre <b-icon icon="file-person"></b-icon></th>
            <th>Apellido <b-icon icon="file-person"></b-icon></th>
            <th>DUI <b-icon icon="card-heading"></b-icon></th>
            <th>Modelo de Carro <b-icon icon="truck"></b-icon></th>
            <th>Precio <b-icon icon="cart"></b-icon></th>
          </tr>
        </thead>
        <tbody>
            <tr v-for="(usuario,index) in usuarios" v-bind:key="usuario">
              <td>{{usuario.nombre}}</td>
              <td>{{usuario.apellido}}</td>
              <td>{{usuario.DUI}}</td>
              <td>{{usuario.modelodecarro}}</td>
              <td>{{usuario.precio}}</td>
              <td><a class="grey darken-4" @click="editar (index)"><b-icon icon="pencil-square"></b-icon></a></td>
              <td><a class= "grey darken-4" @click="eliminar (index)"><b-icon icon="trash-fill"></b-icon></a></td>
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
      indice: -1,
      nombre: '',
      apellido: '',
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
        modelodecarro: this.modelodecarro,
        DUI: this.DUI,
        precio: this.precio
      };
      if(this.indice == -1)
      {
        this.usuarios.push(data);
      }
      else
      {
        this.usuarios[this.indice] = data;
      }
      this.indice = -1;
      this.nombre = '';
      this.apellido = '';
      this.DUI = '';
      this.modelodecarro = '';
      this.precio = 0;
    },
   eliminar(index)
    {
      if(!confirm('¿Desea eliminar este registro?'))return;

      this.usuarios.splice(index, 1);

    },
    editar(index)
    {
      var usuario = this.usuarios[index];
      this.indice = index;
      this.nombre = usuario.nombre;
      this.apellido = usuario.apellido;
      this.DUI = usuario.DUI;
      this.modelodecarro = usuario.modelodecarro;
      this.precio = usuario.precio;




    }
  }
   

}


</script>

<style>

</style>