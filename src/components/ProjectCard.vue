<script setup>
defineProps(['title', 'desc', 'tag'])
</script>

<template>
  <div 
    v-motion
    :initial="{ opacity: 0, filter: 'blur(10px)', y: 10 }"
    :visible-once="{ 
      opacity: 1, 
      filter: 'blur(0px)', 
      y: 0,
      transition: { 
        duration: 800,
        ease: 'easeOut'
      } 
    }"
    class="bg-neutral-900/80 rounded-3xl p-6 border border-neutral-800 hover:border-purple-500/20 hover:bg-neutral-800/90 transition-all duration-700 group cursor-pointer shadow-lg"
  >
    <div class="text-[10px] uppercase tracking-widest text-purple-400 font-bold mb-3 opacity-60 group-hover:opacity-100 transition-opacity">{{ tag }}</div>
    <h3 class="font-bold text-lg mb-2 text-neutral-200 group-hover:text-white transition-colors">{{ title }}</h3>
    <p class="text-xs text-neutral-500 leading-relaxed group-hover:text-neutral-400 transition-colors">{{ desc }}</p>
  </div>
</template>
