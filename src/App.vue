<template>
 <list-usuario :usuarios="usuarios"></list-usuario>
</template>

<script>
import ListUsuario from "./components/ListUsuario.vue";




export default {
  name: 'App',
  components: {
    ListUsuario,
   
  },
   
    


}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
