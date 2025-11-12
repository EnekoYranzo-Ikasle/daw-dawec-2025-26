<script setup>
import { ref } from 'vue';

const contador = ref(0);

function incrementar() {
  return contador.value++;
}

function decrementar() {
  return contador.value--;
}

function restablecer() {
  return (contador.value = 0);
}
</script>

<template>
  <h2>Contador: {{ contador }}</h2>
  <button @click="incrementar">Incrementar</button>
  <button @click="decrementar">Decrementar</button>
  <button @click="restablecer">Restablecer</button>
</template>

<style scoped></style>
