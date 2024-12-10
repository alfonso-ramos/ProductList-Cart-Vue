<script setup>
    const props = defineProps({
        dessert: {
            type: Object,
            required: true
        }
    })

    const emit = defineEmits([
        'addToCart'
    ])
</script>

<template>
    <div class="mx-auto relative mt-6">
        <img class="h-[212px] w-[327px] object-fit rounded-xl" :src="dessert.image.mobile">

        <button 
            type="button"
            class="w-40 h-11 rounded-full border border-rose-400 bg-white flex items-center justify-center absolute bottom-[88px] right-1/4 "
            @click="$emit('addToCart', dessert)"
            >
                <img src="../../public/assets/images/icon-add-to-cart.svg" alt="">
                <p>Add to Cart</p>
        </button>

        <div class="mt-10">
            <p class="text-rose-500">{{ dessert.category }}</p>
            <p class="text-fuchsia-600">{{ dessert.name }}</p>
            <p class="text-red font-semibold text-base">$ {{ dessert.price }}</p>
        </div>
    </div>
</template>


