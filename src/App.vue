<script setup>
 import Header from './components/Header.vue'
 import Hero from './components/Hero.vue'
 import Marketing from  './components/Marketing.vue'
 import Plans from  './components/Plans.vue'
 import OurUsers from  './components/OurUsers.vue'
 import ContactUS from  './components/ContactUS.vue'
 import Footer from  './components/Footer.vue'

</script>

<template>

  <Header />
  <Hero />
  <Marketing />
  <Plans />
  <OurUsers />
  <ContactUS />
  <Footer />

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
