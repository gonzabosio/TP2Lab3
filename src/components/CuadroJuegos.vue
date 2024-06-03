<template>
  <h2>Videojuegos</h2>
  <div class="container">
    <table>
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Estado</th>
          <th>Plataforma</th>
          <th>Puntuación</th>
          <th>Mas Info</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(juego, index) in juegos" :key="index">
          <td>{{ juego.nombre }}</td>
          <td>{{ juego.estado }}</td>
          <td>{{ juego.plataforma }}</td>
          <td>{{ juego.puntaje }}</td>
          <td><button @click="mostrarDetalleJuego(index)">MasInfo</button></td>
        </tr>
      </tbody>
    </table>

    <div v-if="juegoSeleccionado !== null && juegos[juegoSeleccionado]" class="info-seleccionada">
      <p><strong>Nombre:</strong> {{ juegos[juegoSeleccionado].nombre }}</p>
      <p><strong>Estado:</strong> {{ juegos[juegoSeleccionado].estado }}</p>
      <p><strong>Plataforma:</strong> {{ juegos[juegoSeleccionado].plataforma }}</p>
      <p><strong>Puntuación:</strong> {{ juegos[juegoSeleccionado].puntaje }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CuadroJuegos',
  props: {
        juegos: {
            type: Array,
            default: () => []
        }
    },
  data() {
    return {
      juegoSeleccionado: null
    };
  },
  methods: {
    mostrarDetalleJuego(index) {
      this.juegoSeleccionado = index;
    }
  }
}
</script>

<style >
  h2 {
    margin-top: 50px;
  }
  .container {
    display: flex;
  }
  table {
    width: 30%;
    border-collapse: collapse;
    margin-bottom: 20px;
  }
  th, td {
    padding: 12px;
    border: 1px solid #ddd;
    text-align: left;
  }
  th {
    background-color: #f4f4f4;
  }
  .box{
    width: 30%;
    border: 1px solid black;
  }
  .info-seleccionada{
    margin-left: 40px;
    border: 2px solid black;
    width: 400px;
    height: 180px;
  }
  p {
    margin: 20px;
  }
</style>