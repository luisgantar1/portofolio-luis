<script setup>
import { Briefcase, Calendar } from 'lucide-vue-next'

const experiences = [
  {
    company: 'PT. Global Loyalty Indonesia (Alfagift)',
    role: 'Front End Developer',
    period: '6 Bulan',
    desc: 'Fokus pada pengembangan antarmuka pengguna yang responsif dan interaktif. Memastikan konsistensi desain dan pengalaman pengguna yang mulus pada aplikasi Alfagift.',
    tech: ['Vue.js', 'Tailwind CSS', 'Responsive Design', 'JavaScript', 'Bootstrap']
  },
  {
    company: 'PT. Global Loyalty Indonesia (Alfagift)',
    role: 'Full Stack Developer',
    period: '6 Bulan',
    desc: 'Mengembangkan dan memelihara fitur end-to-end pada ekosistem Alfagift. Bertanggung jawab atas integrasi API yang kompleks dan optimasi performa baik di sisi client maupun server.',
    tech: ['JavaScript', 'Vue.js', 'PHP', 'API Integration', 'MYSQL', 'PostgreSQL', 'Python', 'Docker']
  }
]
</script>

<template>
  <section class="mt-24">
    <div class="flex items-center gap-4 mb-12">
      <h2 class="text-3xl font-bold">Experience</h2>
      <div class="h-[1px] flex-1 bg-neutral-800"></div>
    </div>

    <div class="space-y-12 relative before:absolute before:inset-0 before:ml-5 before:-translate-x-px md:before:mx-auto md:before:translate-x-0 before:h-full before:w-0.5 before:bg-gradient-to-b before:from-transparent before:via-neutral-800 before:to-transparent">
      
      <div 
        v-for="(exp, index) in experiences" 
        :key="index"
        v-motion
        :initial="{ opacity: 0, x: index % 2 === 0 ? -20 : 20 }"
        :visible="{ opacity: 1, x: 0, transition: { delay: index * 200 } }"
        class="relative flex items-center justify-between md:justify-normal md:odd:flex-row-reverse group"
      >
        <!-- Icon/Dot -->
        <div class="flex items-center justify-center w-10 h-10 rounded-full border border-neutral-800 bg-neutral-950 text-purple-500 absolute left-0 md:left-1/2 md:-translate-x-1/2 z-10 group-hover:border-purple-500/50 transition-colors shadow-xl">
          <Briefcase :size="18" />
        </div>

        <!-- Card Content -->
        <div class="w-[calc(100%-4rem)] md:w-[45%] bg-neutral-900/40 border border-neutral-800 p-6 rounded-3xl hover:border-purple-500/30 transition-all">
          <div class="flex flex-wrap items-center justify-between gap-2 mb-2">
            <h3 class="text-xl font-bold text-white">{{ exp.role }}</h3>
            <div class="flex items-center gap-2 text-xs text-neutral-500 bg-neutral-800 px-3 py-1 rounded-full">
              <Calendar :size="12" />
              {{ exp.period }}
            </div>
          </div>
          <div class="text-purple-400 font-medium text-sm mb-4">{{ exp.company }}</div>
          <p class="text-neutral-400 text-sm leading-relaxed mb-6">
            {{ exp.desc }}
          </p>
          <div class="flex flex-wrap gap-2">
            <span v-for="t in exp.tech" :key="t" class="text-[10px] uppercase tracking-wider font-bold bg-neutral-800 text-neutral-500 px-2 py-1 rounded">
              {{ t }}
            </span>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>
