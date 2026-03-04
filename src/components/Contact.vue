<script setup>
import { Mail, Linkedin, Github, Sparkles } from 'lucide-vue-next'
</script>

<template>
  <section id="contact" class="mt-24 mb-12">
    <div 
      v-motion
      :initial="{ opacity: 0, y: 50 }"
      :visible="{ opacity: 1, y: 0 }"
      class="bg-neutral-900/50 border border-neutral-800 rounded-[2.5rem] p-8 md:p-12 backdrop-blur-xl relative overflow-hidden"
    >
      <!-- Decorative Glow -->
      <div class="absolute -top-24 -right-24 w-64 h-64 bg-purple-600/20 rounded-full blur-[100px]"></div>
      <div class="absolute -bottom-24 -left-24 w-64 h-64 bg-blue-600/10 rounded-full blur-[100px]"></div>

      <div class="relative z-10">
        <div class="text-center mb-12">
          <div class="inline-flex items-center gap-2 bg-purple-500/10 text-purple-400 px-4 py-2 rounded-full text-sm font-medium mb-6">
            <Sparkles :size="16" />
            <span>Tersedia untuk proyek baru</span>
          </div>
          <h2 class="text-4xl md:text-5xl font-bold mb-6">Mari berdiskusi tentang <span class="text-neutral-500">ide Anda.</span></h2>
          <p class="text-neutral-400 text-lg mb-8">
            Apakah Anda memiliki pertanyaan atau ingin berkolaborasi dalam proyek Machine Learning atau Web Development? Saya siap membantu.
          </p>
        </div>
        
        <div class="max-w-2xl mx-auto space-y-4">
          <a 
            href="mailto:luisgantar1@gmail.com"
            class="flex items-center gap-4 bg-neutral-800/50 border border-neutral-700 rounded-2xl px-6 py-5 hover:border-purple-500 transition-all group"
          >
            <div class="bg-neutral-800 p-3 rounded-2xl group-hover:bg-purple-500 transition-colors">
              <Mail :size="24" class="text-neutral-300 group-hover:text-white" />
            </div>
            <div class="flex-1 text-left">
              <div class="text-sm text-neutral-400">Email</div>
              <div class="text-lg text-neutral-200">luisgantar1@gmail.com</div>
            </div>
          </a>

          <a 
            href="https://www.linkedin.com/in/luis-gantar-9049872b9/"
            target="_blank"
            rel="noopener noreferrer"
            class="flex items-center gap-4 bg-neutral-800/50 border border-neutral-700 rounded-2xl px-6 py-5 hover:border-purple-500 transition-all group"
          >
            <div class="bg-neutral-800 p-3 rounded-2xl group-hover:bg-purple-500 transition-colors">
              <Linkedin :size="24" class="text-neutral-300 group-hover:text-white" />
            </div>
            <div class="flex-1 text-left">
              <div class="text-sm text-neutral-400">LinkedIn</div>
              <div class="text-lg text-neutral-200">linkedin.com/in/luis-gantar/</div>
            </div>
          </a>

          <a 
            href="https://github.com/luisgantar1"
            target="_blank"
            rel="noopener noreferrer"
            class="flex items-center gap-4 bg-neutral-800/50 border border-neutral-700 rounded-2xl px-6 py-5 hover:border-purple-500 transition-all group"
          >
            <div class="bg-neutral-800 p-3 rounded-2xl group-hover:bg-purple-500 transition-colors">
              <Github :size="24" class="text-neutral-300 group-hover:text-white" />
            </div>
            <div class="flex-1 text-left">
              <div class="text-sm text-neutral-400">GitHub</div>
              <div class="text-lg text-neutral-200">github.com/luisgantar1</div>
            </div>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>
