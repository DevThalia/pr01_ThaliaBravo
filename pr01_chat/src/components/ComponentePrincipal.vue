<script setup>
import { ref } from 'vue';
import ComponenteMensaje from './ComponenteMensaje.vue';

const logado = 'Usuario 1';
const mensajes = ref([]); 

const postearMensaje = nuevoMensaje => {
    if(validarMensaje(nuevoMensaje.mensaje)) {
        mensajes.value.push(`${nuevoMensaje.user}: ${nuevoMensaje.mensaje}`);
    }
}

const validarMensaje = mensaje => {
    if (
        typeof mensaje === 'string' &&
        mensaje.trim() !== '' &&
        mensaje.trim().length >= 1
    ) {
        return true;
    } else {
        return false;
    }
}
</script>

<template>
<h1>Chat entre usuarios</h1>
<section>
    <ul>
        <li v-for="(mensaje, index) in mensajes" :key="index">{{ mensaje }}</li>
    </ul>
    <ComponenteMensaje :logado="logado" @mensajeEnviado="postearMensaje" />
</section>
</template>

<style scoped>
</style>
