<script setup>
import { ref } from 'vue'
import ComponenteMensaje from './ComponenteMensaje.vue';

const props = defineProps({
    usuario: String
});

</script>

<template>
<h1>Chat entre usuarios</h1>
<section id="mensajeria">
    <ul>
        Mensajes
        <li>aqui van los mensajes de usuarios</li>
        <li>aqui van los mensajes de usuarios</li>
        <li>aqui van los mensajes de usuarios</li>
        <li>aqui van los mensajes de usuarios</li>
        <li>aqui van los mensajes de usuarios</li>
        <li>aqui van los mensajes de usuarios</li>
    </ul>
</section>
<div id="contieneInputMensajes">
        <ComponenteMensaje/>
    </div>
</template>

<style scoped>
</style>
