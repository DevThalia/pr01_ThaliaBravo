<script setup>
import { ref } from 'vue';
import ComponenteMensaje from './ComponenteMensaje.vue';

const props = defineProps({
    usuario: String
});

const mensajes = ref([]); 

const agregarMensaje = (mensaje) => {
    mensajes.value.push(mensaje); 
}
</script>

<template>
<h1>Chat entre usuarios</h1>
<section id="mensajeria">
    <ul>
        Mensajes
        <li v-for="(mensaje, index) in mensajes" :key="index">{{ mensaje }}</li>
    </ul>
</section>
<div id="contieneInputMensajes">
        <ComponenteMensaje @mensajeEnviado="agregarMensaje" /> 
    </div>
</template>

<style scoped>
</style>
