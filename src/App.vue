<script setup>
import {ref, computed} from 'vue';
var name = "Franz Burneo";

const counter = ref(0);
const styleColor = ref('color: white');

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
                            counter.value < 0 ? 'negative' : 'zero';
})
</script>
<template>
  <h1> Hola {{ name.toUpperCase() }}</h1>
  <h2 :class="classCounter">{{ counter }}</h2>
  <button @click="increment">Incrementar</button>
  <button @click="decrease">Disminuir</button>
  <button @click="reset">Resetear</button>
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