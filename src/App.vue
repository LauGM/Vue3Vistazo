<script setup>
import { ref, reactive } from 'vue';
import HijoComponente from './components/HijoComponente.vue';
//descubrimiento de america es fijo
const descubrimiento = 1492;
//envio puede cambiar con el tiempo
const envio = ref(true);

const contador = ref(0);

const dire='Av Jujuy 778';

//cambiar envio 
envio.value = false;
//objeto reactivo
const usuario = reactive({
  nro: 567,
  categoria: 'A',
  nombre: 'Juan'
});
//cambiar usuario
usuario.categoria='B';
//metodo para incrementar contador
function incrementar(){
  contador.value++;
}
//metodo para decrementar contador
function decrementar(){
  contador.value--;
}
const id=ref(0);
function modificarId(nuevoId){
  id.value=nuevoId;
}
//modificar id
</script>

<template>
  <section>
    <h3>Fecha del descubrimiento de América: {{ descubrimiento }}</h3>
    <select name="envio" v-model="envio">
      <option :value=true>SI</option>
      <option :value=false>NO</option>
    </select>
    <p>{{ usuario.nro }} - {{ usuario.categoria }} - {{ usuario.nombre }}</p>
    <hr>
    <h3>CONTADOR</h3>
    <p>{{ contador }}</p>
    <button @click="incrementar">+</button>
    <button @click="decrementar">-</button>
    <HijoComponente :direccion="dire" @recibir-i-d="modificarId"/>
    <p>ID ACTUAL:{{ id }}</p>
  </section>    
</template>

<style scoped></style>
