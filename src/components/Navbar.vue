<script setup lang="ts">
    import { onMounted, onUpdated } from 'vue'
    import feather from 'feather-icons'
    import { ref } from 'vue';

    onMounted(() => feather.replace())
    onUpdated(() => feather.replace())

    const isOpen = ref(false);

    function toggleMenu(){
        isOpen.value = !isOpen.value;
    }

</script>
<template>
    <nav class="bg-amber-700 fixed w-full z-100">
        <div class="flex md:flex-row  align-center justify-between md:mx-24 mx-12 py-5 text-white">
            <div class="md:hidden flex">
                <button @click="toggleMenu" class="cursor-pointer"><i data-feather="menu"></i></button>
            </div>
            <div class="">
                <h2 class="text-yellow-50 text-2xl font-bold">nasiMbah</h2>
            </div>
            <div class="button-show md:flex hidden">
                <a href="#home" class="px-6 text-yellow-50 hover:text-yellow-300 transition">Home</a>
                <a href="#about" class="px-6 text-yellow-50 hover:text-yellow-300 transition">About</a>
                <a href="#menu" class="px-6 text-yellow-50 hover:text-yellow-300 transition">Menu</a>
                <a href="#contact" class="px-6 text-yellow-50 hover:text-yellow-300 transition">Contact</a>
            </div>
        </div>

        <!-- Dropdown Mobile -->
        <transition
            enter-active-class="transition-all duration-300 ease-out"
            leave-active-class="transition-all duration-300 ease-in"
            enter-from-class="max-h-0 opacity-0"
            enter-to-class="max-h-40 opacity-100"
            leave-from-class="max-h-40 opacity-100"
            leave-to-class="max-h-0 opacity-0"
        >
            <div 
            v-if="isOpen"
            class="md:hidden overflow-hidden bg-amber-700 shadow-md px-6 py-4 mx-6 flex flex-col space-y-3"
            >
                <a href="#home" class="px-6 text-yellow-50 hover:text-yellow-300 transition">Home</a>
                <a href="#about" class="px-6 text-yellow-50 hover:text-yellow-300 transition">About</a>
                <a href="#menu" class="px-6 text-yellow-50 hover:text-yellow-300 transition">Menu</a>
                <a href="#contact" class="px-6 text-yellow-50 hover:text-yellow-300 transition">Contact</a>
            </div>
        </transition>
    </nav>
</template>
<style>

</style>