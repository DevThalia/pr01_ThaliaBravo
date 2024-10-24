<script setup>
import { ref } from 'vue'
const mensaje = ref('');

const guardarMensaje = () => {
    console.log(mensaje.value);
    mensaje.value = '';
}

</script>

<template>
    <input v-model="mensaje" type="text" placeholder="Introduce mensaje">
    <button @click="guardarMensaje()">Enviar</button>
</template>