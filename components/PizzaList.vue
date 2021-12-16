<template>
  <div class="grid">
    <PizzaCard v-for="pizza in pizzas" :key="pizza.id" :pizza="pizza" />
  </div>
</template>
<script>
export default {
  props: {
    pizzas: {
      type: Array,
      default: () => [],
    },
  },
}
</script>
