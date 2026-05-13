<script setup lang="ts">
const phoneNumber = '6289618590705'

const whatsappLink =
  `https://wa.me/${phoneNumber}?text=Halo%20saya%20ingin%20memesan%20menu`
</script>

<template>
  <section
    id="contact"
    class="bg-[#FFF8F0] py-16 px-6 md:px-16"
  >
    <div class="max-w-6xl mx-auto">
      
      <!-- Heading -->
      <div class="text-center mb-12">
        <p class="text-orange-500 font-semibold tracking-wide mb-2">
          Contact
        </p>

        <h2 class="text-4xl font-bold text-gray-800 mb-4">
          Hubungi Kami
        </h2>

        <p class="text-gray-600 max-w-2xl mx-auto leading-relaxed">
          Ingin menikmati masakan rumahan Nusantara yang hangat dan lezat?
          Silakan hubungi kami melalui WhatsApp untuk pemesanan
          dan informasi lebih lanjut.
        </p>
      </div>

      <!-- Content -->
      <div
        class="grid grid-cols-1 md:grid-cols-2 gap-10 items-center"
      >

        <!-- Left -->
        <div
          class="bg-white rounded-3xl shadow-lg p-8"
        >
          <h3 class="text-2xl font-semibold text-gray-800 mb-6">
            Informasi Kontak
          </h3>

          <!-- Address -->
          <div class="mb-5">
            <p class="text-sm text-gray-500 mb-1">
              Alamat
            </p>

            <p class="text-lg text-gray-700">
              Bandung, Jawa Barat
            </p>
          </div>

          <!-- Open Hours -->
          <div class="mb-5">
            <p class="text-sm text-gray-500 mb-1">
              Jam Operasional
            </p>

            <p class="text-lg text-gray-700">
              Senin - Sabtu • 07.00 - 18.00 WIB
            </p>
          </div>

          <!-- WhatsApp -->
          <div class="mb-8">
            <p class="text-sm text-gray-500 mb-1">
              WhatsApp
            </p>

            <p class="text-lg text-gray-700">
              08961-8590-705
            </p>
          </div>

          <!-- Button -->
          <a
            :href="whatsappLink"
            target="_blank"
            class="inline-block bg-green-500 hover:bg-green-600 transition-all duration-300 text-white font-semibold px-6 py-3 rounded-full shadow-md"
          >
          Pesan via WhatsApp
          </a>
        </div>

        <!-- Right -->
        <div
          class="bg-white rounded-3xl shadow-lg overflow-hidden h-[350px]">
            <iframe src="https://www.google.com/maps/embed?pb=!1m17!1m12!1m3!1d1979.8977472572778!2d107.7003527317031!3d-7.033306826088208!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m2!1m1!2s!5e0!3m2!1sid!2sid!4v1778638414126!5m2!1sid!2sid" width="600" height="450" style="border:0;" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>

          <div class="w-full h-full flex items-center justify-center text-gray-400">
          </div>
        </div>

      </div>
    </div>
  </section>
</template>