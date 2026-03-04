<script setup>
import { ref } from 'vue'
import { ExternalLink, Globe, Code2, Palette, Cpu, BrainCircuit, Layout, Database } from 'lucide-vue-next'
import ProjectCard from './ProjectCard.vue'
import ProjectModal from './ProjectModal.vue'

const isModalOpen = ref(false)
const selectedProject = ref(null)

const projects = [
  { 
    title: 'Sentiment Analysis API', 
    desc: 'Deep Learning model deployed with FastAPI & React.', 
    fullDesc: 'Proyek ini menggunakan arsitektur Transformer (BERT) untuk menganalisis sentimen dari ribuan tweet secara real-time. Dilengkapi dengan backend FastAPI yang efisien dan dashboard visualisasi data menggunakan React.',
    tag: 'Machine Learning',
    tech: ['Python', 'PyTorch', 'FastAPI', 'React', 'Tailwind']
  },
  { 
    title: 'Enterprise ERP System', 
    desc: 'Scalable management system built with PHP & Bootstrap.', 
    fullDesc: 'Sistem manajemen sumber daya perusahaan yang mencakup modul inventory, penggajian, dan laporan keuangan. Dibangun dengan fokus pada skalabilitas dan keamanan data tingkat tinggi.',
    tag: 'Web Dev',
    tech: ['PHP', 'MySQL', 'Bootstrap', 'jQuery']
  },
  { 
    title: 'Real-time Stock Monitor', 
    desc: 'Dashboard interaktif menggunakan Vue 3 & Tailwind.', 
    fullDesc: 'Aplikasi pemantauan harga saham secara real-time menggunakan WebSocket. Menampilkan grafik interaktif dan notifikasi perubahan harga yang signifikan.',
    tag: 'Frontend',
    tech: ['Vue 3', 'Tailwind CSS', 'Vite', 'WebSocket']
  }
]

const openModal = (project) => {
  selectedProject.value = project
  isModalOpen.value = true
}
</script>

<template>
  <main id="projects" class="grid grid-cols-1 md:grid-cols-4 gap-4 auto-rows-[180px]">
    <!-- About Card -->
    <div 
      v-motion
      :initial="{ 
        opacity: 0, 
        rotateX: -25,
        y: 40,
        transformPerspective: 1000 
      }"
      :visible-once="{ 
        opacity: 1, 
        rotateX: 0,
        y: 0,
        transition: { 
          duration: 1000,
          delay: 250,
          ease: [0.215, 0.61, 0.355, 1]
        } 
      }"
      class="md:col-span-2 bg-gradient-to-br from-purple-600 to-indigo-800 rounded-3xl p-8 flex items-center justify-between group hover:brightness-110 transition-all duration-500 relative overflow-hidden shadow-xl"
    >
      <div class="absolute inset-0 bg-gradient-to-tr from-transparent via-white/10 to-transparent -translate-x-full group-hover:translate-x-full transition-transform duration-1000"></div>
      <div class="text-white relative z-10">
        <h3 class="text-2xl font-bold mb-1">Passionate Developer</h3>
        <p class="text-purple-100 opacity-80">Menggabungkan logika PHP & Python dengan estetika Tailwind & CSS.</p>
      </div>
      <div class="bg-white/20 p-4 rounded-2xl backdrop-blur-sm group-hover:rotate-6 transition-transform duration-500 relative z-10">
        <Cpu class="text-white" :size="32" />
      </div>
    </div>

    <!-- Tech Stack Grid -->
    <div 
      v-motion
      :initial="{ 
        opacity: 0, 
        rotateX: -25,
        y: 40,
        transformPerspective: 1000 
      }"
      :visible-once="{ 
        opacity: 1, 
        rotateX: 0,
        y: 0,
        transition: { 
          duration: 1000,
          delay: 400,
          ease: [0.215, 0.61, 0.355, 1]
        } 
      }"
      class="md:col-span-1 bg-neutral-900 rounded-3xl p-6 border border-neutral-800 flex flex-col items-center justify-center gap-4 hover:border-blue-500/30 transition-all group relative overflow-hidden shadow-xl"
    >
      <div class="absolute inset-0 bg-gradient-to-tr from-transparent via-white/5 to-transparent -translate-x-full group-hover:translate-x-full transition-transform duration-1000"></div>
      <div class="grid grid-cols-2 gap-4 group-hover:scale-110 transition-transform duration-500 relative z-10">
        <Layout class="text-blue-400" />
        <Database class="text-orange-400" />
        <BrainCircuit class="text-pink-400" />
        <Code2 class="text-green-400" />
      </div>
      <span class="text-sm font-medium text-neutral-400 uppercase tracking-tighter relative z-10 text-center">Stack Terpadu</span>
    </div>

    <!-- Tools Info -->
    <div 
      v-motion
      :initial="{ 
        opacity: 0, 
        rotateX: -25,
        y: 40,
        transformPerspective: 1000 
      }"
      :visible-once="{ 
        opacity: 1, 
        rotateX: 0,
        y: 0,
        transition: { 
          duration: 1000,
          delay: 550,
          ease: [0.215, 0.61, 0.355, 1]
        } 
      }"
      class="md:col-span-1 bg-neutral-900 rounded-3xl p-6 border border-neutral-800 flex flex-col items-center justify-center text-center hover:border-orange-500/30 transition-all group relative overflow-hidden shadow-xl"
    >
      <div class="absolute inset-0 bg-gradient-to-tr from-transparent via-white/5 to-transparent -translate-x-full group-hover:translate-x-full transition-transform duration-1000"></div>
      <div class="text-xs text-neutral-500 mb-1 relative z-10">Framework Favorit</div>
      <div class="font-bold text-white group-hover:text-orange-400 transition-colors relative z-10">FastAPI + React</div>
      <div class="w-full h-1 bg-neutral-800 rounded-full mt-3 overflow-hidden relative z-10">
        <div class="w-3/4 h-full bg-gradient-to-r from-orange-500 to-purple-500 group-hover:w-full transition-all duration-1000"></div>
      </div>
    </div>

    <!-- Dynamic Projects -->
    <ProjectCard 
      v-for="(project, index) in projects" 
      :key="index"
      :title="project.title"
      :desc="project.desc"
      :tag="project.tag"
      @click="openModal(project)"
      class="cursor-pointer"
      :style="{ transitionDelay: `${index * 100}ms` }"
    />
  </main>

  <!-- Modal Component -->
  <ProjectModal 
    :project="selectedProject" 
    :isOpen="isModalOpen" 
    @close="isModalOpen = false" 
  />
</template>
