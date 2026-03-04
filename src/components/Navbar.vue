<script setup>
import { Github, Linkedin, Mail, FileDown } from 'lucide-vue-next'
</script>

<template>
  <nav class="flex justify-between items-center mb-16" v-motion-fade>
    <div class="text-2xl font-bold bg-gradient-to-r from-purple-400 to-pink-600 bg-clip-text text-transparent">
      LUIS.
    </div>
    <div class="flex items-center gap-4 md:gap-8">
      <div class="hidden md:flex gap-6 items-center">
        <a 
          href="https://github.com/luisgantar1" 
          target="_blank" 
          rel="noopener noreferrer" 
          class="text-neutral-400 hover:text-purple-400 transition-colors"
        >
          <Github :size="20" />
        </a>
        <a 
          href="https://www.linkedin.com/in/luis-gantar-9049872b9/" 
          target="_blank" 
          rel="noopener noreferrer" 
          class="text-neutral-400 hover:text-purple-400 transition-colors"
        >
          <Linkedin :size="20" />
        </a>
      </div>
      
      <a 
        href="/public/cv/cv_luisgantar.pdf" 
        download
        class="flex items-center gap-2 bg-neutral-900 border border-neutral-800 px-5 py-2.5 rounded-full text-sm font-medium hover:bg-neutral-800 transition-all hover:border-neutral-700 group"
      >
        <FileDown :size="18" class="text-purple-400 group-hover:scale-110 transition-transform" />
        <span>Download CV</span>
      </a>
    </div>
  </nav>
</template>
