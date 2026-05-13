<script setup lang="ts">
  import Navbar from './components/Navbar.vue';
  import Hero from './sections/Hero.vue';
  import About from './sections/About.vue';
  import Menu from './sections/Menu.vue';
  import Contact from './sections/Contact.vue';
  import Footer from './components/Footer.vue';
</script>

<template>
  <!-- Header -->
  <header class="bg-sky-300 z-100">
    <Navbar />
  </header>

  <!-- Body -->
  <section id="home" class="py-8">
    <Hero />
  </section>

  <section id="about" class="py-8">
    <About />
  </section>

  <section id="menu" class="py-8">
    <Menu />
  </section>

  <section id="contact">
    <Contact />
  </section>

  <!-- Footer -->
  <Footer />
</template>
