<template>
  <div class="px-5">
    <PizzaList :pizzas="pizzas" />
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'IndexPage',

  async asyncData() {
    const response = await axios.get(
      'http://pizza.test/wp-json/pizza/v1/pizzas'
    )
    return { pizzas: response.data }
  },
}
</script>
