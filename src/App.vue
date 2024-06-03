<template>
  <div id="app">
   
    <TableComponent />
  </div>
</template>

<script  >
import TableComponent from './components/CuadroJuegos.vue';

export default {
  name: 'App',
  components: {
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
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  
}
</style>