<template>
  <div>
    <h2>Videojuegos</h2>
    <table>
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Estado</th>
          <th>Plataforma</th>
          <th>Puntuación</th>
          <th>MasInfo</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(juego, index) in juegos" :key="index">
          <td>{{ juego.nombre }}</td>
          <td>{{ juego.estado }}</td>
          <td>{{ juego.plataforma }}</td>
          <td>{{ juego.puntuacion }}</td>
          <td><button @click="mostrarDetalleJuego(index)">MasInfo</button></td>
        </tr>
      </tbody>
    </table>

    <div v-if="juegoSeleccionado !== null" class="info-seleccionada">
      <p><strong>Nombre:</strong> {{ juegos[juegoSeleccionado].nombre }}</p>
      <p><strong>Estado:</strong> {{ juegos[juegoSeleccionado].estado }}</p>
      <p><strong>Plataforma:</strong> {{ juegos[juegoSeleccionado].plataforma }}</p>
      <p><strong>Puntuación:</strong> {{ juegos[juegoSeleccionado].puntuacion }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      juegos: [
        { nombre: 'gta', estado: 'inicio', plataforma: 'PC', puntuacion: 9 },
      ],
      juegoSeleccionado: null
    };
  },
  methods: {
    mostrarDetalleJuego(index) {
      this.juegoSeleccionado = index;
    }
  },
 
};
</script>
  <style >
 
  table {
    margin-top: 40px;
    width: 30%;
    border-collapse: collapse;
    margin: 40px 40px;

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
    float: left;
}
  .info-seleccionada{
    border: 2px solid black;
    width: 30%;
  }
  </style>