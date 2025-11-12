<script setup>
import { reactive } from 'vue';

const texto = reactive({
  normal: '',
  mayusculas: '',
});

function actualizar() {
  texto.normal = event.target.value;
  texto.mayusculas = event.target.value.toUpperCase();
}
</script>

<template>
  <input type="text" @input="actualizar" placeholder="Tu nombre" />
  <p>Normal: {{ texto.normal }}</p>
  <p>En mayúsculas: {{ texto.mayusculas }}</p>
</template>

<style scoped></style>
