<template>
  <div class="px-5 h-screen grid place-items-center">
    <label for="search">
      <input
        id="search"
        v-model="search"
        class="border-2 border-black px-5 py-2"
        type="text"
        name="search"
        placeholder="Search for Pizza"
      />
    </label>
    <PizzaList :pizzas="searchPizza" />
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

  data() {
    return {
      search: '',
    }
  },
  computed: {
    searchPizza() {
      const pizza = this.pizzas.filter((singlePizza) => {
        return singlePizza?.post_name
          .toLowerCase()
          .includes(this.search.toLowerCase())
      })
      return pizza.length > 0 ? pizza : this.pizzas
    },
  },
}
</script>
