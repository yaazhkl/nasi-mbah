<script setup lang="ts">
    defineProps<{
        title: string
        price: number
        image: string
        description: string
    }> ()
</script>
<template>
    <div class="p-6">
        <img :src="image" :alt="title" class="w-full object-cover h-72 rounded">

        <h2 class="text-center mb-4 mt-3 font-bold text-xl">{{ title }}</h2>

        <p>{{ description }}</p>

        <p class="font-bold">Rp. {{ price.toLocaleString('id-ID') }}</p>
    </div>
</template>
<style>
</style>