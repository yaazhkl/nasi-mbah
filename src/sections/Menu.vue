<script setup lang="ts">
import { ref } from 'vue';
import { onMounted } from 'vue';
import MenuCard from '../menu/MenuCard.vue';

     const favoriteMenu = [
    {
    title: 'Ayam Serundeng',
    price: 8000,
    image: '/src/assets/ayam-serundeng.jpg',
    description: 'Ayam goreng rempah dengan taburan kelapa serundeng gurih.'
  },
  {
    title: 'Telur Balado',
    price: 5000,
    image: '/src/assets/telur-balado.jpg',
    description: 'Telur berbumbu sambal balado pedas manis.'
  },
    {
    title: 'Kwetiau Goreng',
    price: 5000,
    image: '/src/assets/kwetiau-goreng.jpg',
    description: 'Kwetiau tumis gurih dengan kecap dan sayuran.'
  }
];

    interface Menu{
        title : string;
        price : number;
        image : string;
        description : string;
    }

    const listMenu = ref<Menu[]>([]); 

    async function fetchMenu() {
        try {
            const response = await fetch("/data/data.json");
            if (!response.ok) {
                throw new Error("Gagal mengambil data");
            }
            const data = await response.json();
            listMenu.value = data.menu;
            console.log(listMenu.value);
        } catch(error) {
        console.error("Error:", error);
        }
    }
    
    onMounted(() =>{
        fetchMenu();
    })

</script>
<template>
    <section class="py-16 bg-gradient-to-b from-sky-[#fad2b4] to-white">
        <div class="max-w-7xl mx-auto px-6"> 
            <div class="text-center mb-12">
            <p class="text-yellow-600 font-semibold tracking-widest uppercase mb-2">
            Best Seller
            </p>

            <h2 class="text-4xl font-extrabold text-gray-800">
                Menu Favorit
            </h2>

            <p class="text-gray-500 mt-3 max-w-2xl mx-auto">
                Pilihan menu favorit pelanggan dengan cita rasa terbaik dan bahan berkualitas.
            </p>
            </div> 

            <!-- Card Container -->
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8"> 

            <MenuCard
                v-for="favorite in favoriteMenu"
                :key="favorite.title"
                :title="favorite.title"
                :price="favorite.price"
                :image="favorite.image"
                :description="favorite.description"

                class="bg-white rounded-3xl overflow-hidden 
                    shadow-md hover:shadow-2xl
                    transition-all duration-300
                    hover:-translate-y-2 border border-gray-100"
            />

            </div>
        </div>

        <!-- All Menu -->

        <div class="text-center mb-12 pt-15 pb-8">
            <h2 class="text-4xl font-extrabold text-gray-800">
                List Semua Menu
            </h2>

            <p class="text-gray-500 mt-3 max-w-2xl mx-auto">
                Pilihan menu favorit pelanggan dengan cita rasa terbaik dan bahan berkualitas.
            </p>
            <!-- Card Container -->
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">

            <MenuCard
                v-for="menu in listMenu"
                :key="menu.title"
                :title="menu.title"
                :price="menu.price"
                :image="menu.image"
                :description="menu.description"

                class="bg-white rounded-3xl overflow-hidden 
                    shadow-md hover:shadow-2xl
                    transition-all duration-300
                    hover:-translate-y-2 border border-gray-100"
            />

            </div>

        </div>
        <!-- All Menu End -->
    </section>      


</template>