<template>
  <div>
    <div class="card" style="width: 14rem; display: inline-table" v-for="usuario in usuarios" :key="usuario.name.title">
      <img class="card-img-top" :src="usuario.picture.large" alt="Card image cap" />
      <div class="card-body">
        <h5 class="card-title">
          {{ usuario.name.title }} {{ usuario.name.first }}
          {{ usuario.name.last }}
        </h5>
        <ul class="list-group">
          <li class="list-group-item">Genero: {{ usuario.gender }}</li>
          <li class="list-group-item">Pais: {{ usuario.location.country }}</li>
          <li v-if="usuario.dob.age > 18" class="list-group-item list-group-item-success">
            Edad: {{ usuario.dob.age }}
          </li>
          <li v-else class="list-group-item list-group-item-danger">
            Edad: {{ usuario.dob.age }}
          </li>
          
        </ul>
        <button v-if="usuario.gender == 'male'" type="button" class="btn btn-primary" id="boton1" @click="show = !show"> Ver más </button>
        <button v-else type="button" class="btn btn-danger" id="boton2" @click="show = !show"> Ver más </button>

        <div id="mostrar2" v-show="show">
          <li id="toggle1" class="list-group-item" >
            E-mail: {{ usuario.email }}
          </li>
          <li id="toggle2" class="list-group-item">
            Ciudad: {{ usuario.location.city }}
          </li>
        </div>

      </div>
    </div>
  </div>
</template>

<script>

import json from "../assets/users.json";

export default {
  name: "list-usuario",

  data() {
    return {
      usuarios: json,
    };
  },
  /*function(){
    return{
      show: true
    }
  }*/
};
</script>

<style>

</style>
