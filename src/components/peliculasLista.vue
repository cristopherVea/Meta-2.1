<!-- src/components/Peliculas.vue -->
<template>
  <div>
    <h1>Películas</h1>
    <div v-if="peliculaSeleccionada">
      <h2>Película seleccionada: {{ peliculaSeleccionada.movie }}</h2>
    </div>
    <table>
      <thead>
        <tr>
          <th>Título</th>
          <th>Calificacion </th>
          <th>Url</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="pelicula in peliculas" :key="pelicula.id" @click="seleccionarPelicula(pelicula)">
          <td>{{ pelicula.movie }}</td>
          <td>{{ pelicula.rating }}</td>
          <td>{{ pelicula.imdb_url }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const peliculas = ref([]);
const peliculaSeleccionada = ref(null);

onMounted(async () => {
  try {
    const response = await fetch('https://dummyapi.online/api/movies');
    const data = await response.json();
    peliculas.value = data;
  } catch (error) {
    console.error('Error al obtener las películas:', error);
  }
});

const seleccionarPelicula = (pelicula) => {
  peliculaSeleccionada.value = pelicula;
};
</script>

<style scoped>
table {
  width: 100%;
  border-collapse: collapse;
}
th, td {
  border: 1px solid #ddd;
  padding: 8px;
  text-align: left;
}
th {
  background-color: #f2f2f2;
}
tr:hover {
  background-color: #f5f5f5;
  cursor: pointer;
}
</style>