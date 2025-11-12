<script setup>
import { ref } from 'vue';

const text = ref('');

function actualizar() {
  return (text.value = event.target.value);
}
</script>

<template>
  <input type="text" @input="actualizar" placeholder=" Escribe algo ..." />
  <p>Has escrito: {{ text }}</p>
</template>

<style scoped></style>
