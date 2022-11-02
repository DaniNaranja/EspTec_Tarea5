<template>
  <div>
    <div class="card" style="width: 14rem; display:inline-table;" v-for="usuario in usuarios" :key="usuario.name.title">
      <img class="card-img-top" :src="usuario.picture.medium" alt="Card image cap" />
      <div class="card-body">
        <h5 class="card-title">{{ usuario.name.title }} {{ usuario.name.first }} {{ usuario.name.last }}</h5>
        <ul class="list-group">
          <li class="list-group-item">Genero: {{ usuario.gender }}</li>
          <li class="list-group-item">Pais: {{ usuario.location.country }}</li>
          <li v-if="usuario.dob.age > 18" class="list-group-item list-group-item-success">Edad: {{usuario.dob.age}}</li>
          <li v-else class="list-group-item list-group-item-danger">Edad: {{usuario.dob.age}}</li>
          <br />
        </ul>

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
};
</script>

<style>

</style>
