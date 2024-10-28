<script setup>
import { ref, defineEmits } from 'vue';

const emit = defineEmits(['mensajeEnviado']);
const mensaje = ref('');

const guardarMensaje = () => {
    emit('mensajeEnviado', mensaje.value); // Emitimos el mensaje
    mensaje.value = '';
}
</script>

<template>
    <input v-model="mensaje" type="text" placeholder="Introduce mensaje">
    <button @click="guardarMensaje()">Enviar</button>
</template>

<style scoped>
</style>
