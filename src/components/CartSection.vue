<script setup>
    const props = defineProps({
        cart: {
            type: Array,
            required: true
        },
        dessert: {
            type: Object,
            required: true
        }
    })


</script>

<template>
    <h2>Your Cart ({{ cart.length }})</h2>
    <div v-if="cart.length === 0">
        <img src="../../public/assets/images/illustration-empty-cart.svg" alt="">
        <p>Your added items will appear here</p>
    </div>
    <div v-else>
        <div v-for="product in cart" :key="product.id">
            <p>{{ product.name }}</p>
            <div class="flex">
                <p>{{ product.ammount }}x</p>
                <p>@ ${{ product.price }}</p>
                <p>${{ product.price * product.ammount }}</p>
            </div>
        </div>
    </div>
</template>

