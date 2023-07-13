<script setup>
  const name = 'Vue dinámico'
  const arrayFrutas = [
        {
            name: "Manzana",
            price: "$1.00",
            description: "Una manzana",
        },
        {
            name: "Pera",
            price: "$2.00",
            description: "Una pera",
        },
        {
            name: "Naranja",
            price: "$3.00",
            description: "Una naranja",
        },
    ];
</script>
<template>
  <h1 class="title">Hola mundo desde {{name.toUpperCase()}}</h1>
  <ul>
    <li
      v-for="fruta in arrayFrutas"
      :key="fruta.name"
    >
      <h1 class="fruta-title">
        Fruta: {{ fruta.name }}
      </h1>
      <h2>
        Descripción: {{ fruta.description }}
      </h2>
      <h2>
        Precio: {{ fruta.price }}
      </h2>
    </li>
  </ul>
</template>

<style>
  .title{
    color: red;
  }
  .fruta-title{
    color: blue;
  }
</style>