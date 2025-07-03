<script setup lang="ts">
import HeaderComponent from './components/HeaderComponent.vue'
import HeroSection from './components/HeroSection.vue'
import ProductsSection from './components/ProductsSection.vue'
import AboutSection from './components/AboutSection.vue'
import ContactSection from './components/ContactSection.vue'
import FooterComponent from './components/FooterComponent.vue'
</script>

<template>
  <div id="app">
    <HeaderComponent />
    
    <main>
      <HeroSection />
      <ProductsSection />
      <AboutSection />
      <ContactSection />
    </main>

    <FooterComponent />
  </div>
</template>

<style>
/* Reset en Global Styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

html, body {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}

body {
  font-family: 'Comic Neue', cursive;
  line-height: 1.6;
  color: #333;
}

#app {
  width: 100%;
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}

main {
  width: 100%;
}

section {
  display: block;
  width: 100%;
}

header, footer {
  display: block;
  width: 100%;
}
</style>
