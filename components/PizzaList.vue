<template>
  <div
    class="card-list grid gap-24 mb-20 sm:grid-cols-2 sm:gap-5 md:gap-5 lg:grid-cols-4"
  >
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
