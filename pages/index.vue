<template>
  <div class="px-5 md:px-20 grid gap-20 lg:max-w-7xl lg:mx-auto">
    <HeroSection />
    <label for="search" class="justify-self-end">
      <input
        id="search"
        v-model="search"
        class="shadow-2xl px-5 py-2 text-xl"
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
