<script setup>
import { 
  Terminal, 
  Cpu, 
  Layers, 
  Box 
} from 'lucide-vue-next'

const skillCategories = [
  {
    name: 'Languages',
    icon: Terminal,
    skills: ['Python', 'JavaScript', 'PHP', 'HTML/CSS']
  },
  {
    name: 'Frameworks & Libraries',
    icon: Layers,
    skills: ['FastAPI', 'Vue.js', 'React.js', 'Tailwind CSS', 'Bootstrap']
  },
  {
    name: 'Fields of Interest',
    icon: Cpu,
    skills: ['Machine Learning', 'Web Development', 'API Design']
  }
]
</script>

<template>
  <section class="mt-24">
    <div class="flex items-center gap-4 mb-12">
      <h2 class="text-3xl font-bold">Tech Stack</h2>
      <div class="h-[1px] flex-1 bg-neutral-800"></div>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      <div 
        v-for="(category, index) in skillCategories" 
        :key="index"
        v-motion
        :initial="{ opacity: 0, y: 20 }"
        :visible="{ opacity: 1, y: 0, transition: { delay: index * 100 } }"
        class="bg-neutral-900/30 border border-neutral-800 p-8 rounded-3xl hover:border-purple-500/30 transition-colors group"
      >
        <div class="flex items-center gap-4 mb-6">
          <div class="p-3 bg-neutral-800 rounded-2xl group-hover:bg-purple-500/10 group-hover:text-purple-400 transition-colors">
            <component :is="category.icon" :size="24" />
          </div>
          <h3 class="font-bold text-xl">{{ category.name }}</h3>
        </div>
        
        <div class="flex flex-wrap gap-2">
          <span 
            v-for="skill in category.skills" 
            :key="skill"
            class="px-4 py-2 bg-neutral-800/50 border border-neutral-700/50 rounded-xl text-sm text-neutral-400 hover:text-white hover:border-neutral-500 transition-all cursor-default"
          >
            {{ skill }}
          </span>
        </div>
      </div>
    </div>
  </section>
</template>
