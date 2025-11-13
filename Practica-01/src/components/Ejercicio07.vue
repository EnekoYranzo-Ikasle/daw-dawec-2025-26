<script setup>
import { reactive } from 'vue';

const listaUsuarios = reactive({
  usuarios: [
    {
      nombre: '',
      edad: '',
      ciudad: '',
    },
  ],
});

function actualizar(indice, campo) {
  listaUsuarios.usuarios[indice][campo] = event.target.value;
}
</script>

<template>
  <div v-for="(usuario, index) in listaUsuarios.usuarios" :key="index">
    <input
      type="text"
      :value="usuario.nombre"
      @input="(e) => actualizar(index, 'nombre')"
      placeholder="Nombre"
    />
    <input
      type="text"
      :value="usuario.edad"
      @input="(e) => actualizar(index, 'edad')"
      placeholder="Edad"
    />
    <input
      type="text"
      :value="usuario.ciudad"
      @input="(e) => actualizar(index, 'ciudad')"
      placeholder="Ciudad"
    />
  </div>

  <ul>
    <li v-for="t in listaUsuarios.usuarios">
      {{ t.nombre }} tiene {{ t.edad }} años y vive en {{ t.ciudad }}
    </li>
  </ul>
</template>

<style scoped></style>
