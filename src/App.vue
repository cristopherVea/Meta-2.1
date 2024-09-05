<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Peliculas from './components/peliculasLista.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <Peliculas />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
  display: flex;
  align-items: flex-start; /* Alinea el contenido hacia arriba */
  padding: 0.5rem; /* Espacio alrededor del encabezado */
  margin-bottom: 10rem; /* Añade espacio hacia abajo */
}

.logo {
  margin: 0; /* Elimina cualquier centrado automático */
  padding-right: 1rem; /* Añade algo de espacio a la derecha del logo */
}

header .wrapper {
  display: flex;
  align-items: flex-start; /* Alinea el contenido de la izquierda */
  flex-wrap: wrap;
}
</style>
