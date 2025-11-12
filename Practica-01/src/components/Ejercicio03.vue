<script setup>
import { reactive } from 'vue';

const usuario = reactive({
  nombre: 'Ana',
  edad: 20,
  email: 'ana@example.com',
});

function cumplirAnnos() {
  return usuario.edad++;
}
</script>

<template>
  <h2>{{ usuario.nombre }} ({{ usuario.edad }})</h2>
  <p>{{ usuario.email }}</p>
  <button @click="cumplirAnnos">Cumplir años</button>
</template>

<style scoped></style>
