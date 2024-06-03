<template>
  <h1>Administrador de videojuegos</h1>
    <NuevoJuegoForm />
    <TableComponent />
</template>

<script>
import NuevoJuegoForm from './components/NuevoJuegoForm.vue';
import TableComponent from './components/CuadroJuegos.vue';

export default {
  name: 'App',
  components: {
    NuevoJuegoForm,
    TableComponent
  }
};
</script>

<style>
h1{
  float: left;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin: 30px;
}
</style>