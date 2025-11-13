<script setup>
import { reactive, computed } from 'vue';

const tienda = reactive({
  carrito: [
    {
      nombre: 'Libro',
      precio: 15,
    },
    {
      nombre: 'Café',
      precio: 3,
    },
    {
      nombre: 'Bolígrafo',
      precio: 2,
    },
  ],
});

const total = computed(() => {
  let suma = 0;

  for (const i in tienda.carrito) {
    suma += tienda.carrito[i].precio;
  }

  return suma;
});
</script>

<template>
  <h2>Carrito</h2>
  <ul>
    <li v-for="t in tienda.carrito">{{ t.nombre }} - ${{ t.precio }}</li>
  </ul>
  <p>Total: ${{ total }}</p>
</template>

<style scoped></style>
