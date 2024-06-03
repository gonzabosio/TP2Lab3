<template>
    <NuevoJuegoForm @nuevo-juego = "agregarJuego"/>
    <CuadroJuegos :juegos="listaJuegos"/>
</template>

<script>
import NuevoJuegoForm from './components/NuevoJuegoForm.vue';
import CuadroJuegos from './components/CuadroJuegos.vue';

export default {
  name: 'App',
  components: {
    NuevoJuegoForm,
    CuadroJuegos
  },
  data() {
        return {
            listaJuegos: []
        };
    },
  methods: {
    agregarJuego(formData) {
      this.listaJuegos.push(formData);
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin: 30px;
}
</style>