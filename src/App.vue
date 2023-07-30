<script setup>
import {ref, computed} from 'vue';
var name = "Franz Burneo";

const counter = ref(0);
const styleColor = ref('color: white');
const listaNumeros = ref([]);

const increment = () => {
  counter.value++;
}
const decrease = () => {
  counter.value--;
}
const reset = () => {
  counter.value = 0;
}
const classCounter = computed(() => {
  return counter.value > 0 ? 'positive' :
                            counter.value < 0 ? 'negative' :
                             'zero';
})

const added = computed(() => {
  return listaNumeros.value.includes(counter.value) ? true : false;
})

const add = () =>{
  listaNumeros.value.push(counter.value);
}
</script>
<template>
  <h1> Hola {{ name.toUpperCase() }}</h1>
  <h2 :class="classCounter">{{ counter }}</h2>
  <button @click="increment" class="btn btn-success">Incrementar</button>
  <button @click="decrease" class="btn btn-danger">Disminuir</button>
  <button @click="reset" class="btn btn-primary">Resetear</button>
  <button @click="add" class="btn btn-warning" :disabled="added">Add</button>
  <h2 >{{ listaNumeros }}</h2>
</template>


<style>
h1{
  color: brown;
}
.positive{
  color: green;
}
.negative{
  color: red;
}
.zero {
  color: peru;
}
</style>