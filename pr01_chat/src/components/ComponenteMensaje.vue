<script setup>
import { ref, defineEmits } from 'vue';

const props = defineProps({
    logado: String
})

let user = props.logado;
let mensaje = ref('');

const emit = defineEmits(['mensajeEnviado']);

const guardarMensaje = () => {
    emit('mensajeEnviado', { user, mensaje: mensaje.value });
    mensaje.value = '';  // Limpiar el campo de entrada después de enviar
}
</script>

<template>
    <section>
        <input v-model="mensaje" type="text" placeholder="Escribe un mensaje" />
        <button @click="guardarMensaje">Enviar</button>
    </section>
</template>

<style scoped></style>
