<script setup>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import BentoGrid from './components/BentoGrid.vue'
import TechStack from './components/TechStack.vue'
import Experience from './components/Experience.vue'
import Contact from './components/Contact.vue'
import Background from './components/Background.vue'
</script>

<template>
  <div class="min-h-screen bg-transparent text-white p-6 md:p-12 font-sans selection:bg-purple-500/30">
    <Background />
    <div class="max-w-6xl mx-auto">
      <Navbar />
      <Hero />
      <BentoGrid />
      <TechStack />
      <Experience />
      <Contact />

      <!-- Footer -->
      <footer class="mt-24 pt-8 border-t border-neutral-800 text-center text-neutral-500 text-sm">
        <p>&copy; 2026 Luis Portfolio. Built with Vue 3 & Tailwind v4.</p>
      </footer>
    </div>
  </div>
</template>

<style>
/* Smooth Scroll */
html {
  scroll-behavior: smooth;
}

/* Custom Selection Color */
::selection {
  background: rgba(168, 85, 247, 0.4);
  color: white;
}
</style>
