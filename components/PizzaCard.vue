<template>
  <div
    class="bg-white px-10 pb-10 grid gap-5 shadow-2xl rounded-xl hover:shadow-2xl"
  >
    <figure
      class="relative rounded-full h-36 w-36 transform -translate-y-1/4 shadow-2xl justify-self-center"
    >
      <img
        :src="pizza.acf.image.url"
        alt=""
        class="absolute top-0 left-0 rounded-full h-full w-100 object-cover border-4 border-white"
      />
    </figure>
    <h2 class="text-3xl font-text capitalize font-bold">
      {{ pizza.post_name }}
    </h2>
    <p class="font-text font-medium">{{ pizza.acf.ingredients }}</p>
    <p class="font-text font-bold text-2xl">{{ pizza.acf.price }} €</p>
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
