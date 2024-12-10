<script setup>
  import {ref} from 'vue'
  import data from "../data.json"
  import ArticleCard from "./components/ArticleCard.vue"
  import CartSection from "./components/CartSection.vue"

  const cart = ref([])
  const desserts = ref([])
  const dessert = ref([])

  const addToCart = (dessert) => {
    const existInCart = cart.value.findIndex(product => product.id === dessert.id)

    if(existInCart >= 0) {
      cart.value[existInCart].ammount++
    } else {
      dessert.ammount = 1
      cart.value.push(dessert)
    }
  }
</script>

<template>
  <main class="mt-6 mx-auto">
    <h1 class="text-4xl font-bold text-rose-900">Desserts</h1>
    <div class="flex flex-col mt-8 md:grid md:grid-cols-3 md:max-w-[688px] md:mx-auto md:gap-6">
      <ArticleCard 
        v-for="dessert in data"
        :key="dessert"
        :dessert="dessert"
        @addToCart="addToCart"
      />
    </div>
  </main>
  <CartSection 
    :cart="cart"
    :dessert="dessert"
  
  />

</template>
