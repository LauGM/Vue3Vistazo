<script setup>
    const props=defineProps({
        direccion:String,
    })
    const emit=defineEmits(['recibirID'])
</script>

<template>
    <p>Direccion: {{ props.direccion }}</p>
    <button @click="emit('recibirID',908744)">Enviar nuevo ID</button>
</template>


<style scoped>

</style>