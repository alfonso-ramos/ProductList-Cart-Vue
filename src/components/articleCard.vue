<script setup>
import CartButton from './CartButton.vue';

    const props = defineProps({
        dessert: {
            type: Object,
            required: true
        }
    })
</script>

<template>
    <div>
        <img class="h-[212px] w-[327px] object-fit rounded-xl" :src="dessert.image.mobile">
        <CartButton />
        <p class="text-fuchsia-600">{{ dessert.name }}</p>
        <p>{{ dessert.category }}</p>
        <p>$ {{ dessert.price }}</p>
    </div>
</template>


