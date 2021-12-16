<template>
  <div>
    <img :src="pizza.acf.image.url" alt="" />
    <h2>{{ pizza.post_name }}</h2>
    <p>{{ pizza.acf.ingredients }}</p>
    <p>{{ pizza.acf.price }} €</p>
  </div>
</template>
<script>
export default {
  props: {
    pizza: {
      type: Object,
      default: () => {},
    },
  },
}
</script>
