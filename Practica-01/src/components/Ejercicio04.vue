<script setup>
import { reactive, ref } from 'vue';

const tareaNueva = ref('');

const estado = reactive({
  tareas: [],
});

function agregarTarea() {
  if (tareaNueva.value.trim() !== '') {
    estado.tareas.push(tareaNueva.value);
    tareaNueva.value = '';
  }
}
</script>

<template>
  <h2>Mis tareas ({{ estado.tareas.length }})</h2>
  <input type="text" v-model="tareaNueva" placeholder="Escribe una tarea" />
  <ul>
    <li v-for="t in estado.tareas">{{ t }}</li>
  </ul>
  <button @click="agregarTarea">Agregar tarea</button>
</template>

<style scoped></style>
