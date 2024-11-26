<script setup>
import articleCard from "./components/articleCard.vue"

import desserts from "../data.json"
</script>

<template>
  <main class="mt-6">
    <h1 class="text-4xl font-bold text-rose-900">Desserts</h1>
    <div>
      <articleCard 
        v-for="dessert in desserts"
        :dessert="dessert"
      />

    </div>
  </main>
</template>

<style scoped>

</style>
