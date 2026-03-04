<script setup>
import { X, ExternalLink, Github, Code2, Cpu } from 'lucide-vue-next'

const props = defineProps(['project', 'isOpen'])
const emit = defineEmits(['close'])
</script>

<template>
  <Transition
    enter-active-class="transition duration-300 ease-out"
    enter-from-class="opacity-0"
    enter-to-class="opacity-100"
    leave-active-class="transition duration-200 ease-in"
    leave-from-class="opacity-100"
    leave-to-class="opacity-0"
  >
    <div v-if="isOpen" class="fixed inset-0 z-50 flex items-center justify-center p-4 md:p-6">
      <!-- Backdrop -->
      <div class="absolute inset-0 bg-black/80 backdrop-blur-sm" @click="emit('close')"></div>
      
      <!-- Modal Content -->
      <div 
        v-motion
        :initial="{ opacity: 0, scale: 0.9, y: 20 }"
        :enter="{ opacity: 1, scale: 1, y: 0 }"
        class="bg-neutral-900 border border-neutral-800 w-full max-w-3xl max-h-[90vh] rounded-[2.5rem] overflow-hidden overflow-y-auto relative z-10 shadow-2xl"
      >
        <button 
          @click="emit('close')"
          class="absolute top-6 right-6 p-2 bg-neutral-800 hover:bg-neutral-700 rounded-full transition-colors z-20"
        >
          <X :size="20" />
        </button>

        <div class="grid md:grid-cols-2">
          <!-- Image/Visual Placeholder -->
          <div class="h-64 md:h-auto bg-gradient-to-br from-purple-600/20 to-blue-600/20 flex items-center justify-center border-b md:border-b-0 md:border-r border-neutral-800 relative group">
            <div class="absolute inset-0 bg-neutral-950/40 group-hover:bg-transparent transition-colors"></div>
            <component :is="project.tag === 'Machine Learning' ? Cpu : Code2" :size="80" class="text-purple-500/50" />
          </div>

          <!-- Text Content -->
          <div class="p-8 md:p-10">
            <div class="inline-flex items-center gap-2 bg-purple-500/10 text-purple-400 px-3 py-1 rounded-full text-xs font-medium mb-6">
              {{ project.tag }}
            </div>
            <h2 class="text-3xl font-bold mb-4">{{ project.title }}</h2>
            <p class="text-neutral-400 leading-relaxed mb-8">
              {{ project.fullDesc || project.desc }}
            </p>

            <div class="space-y-6">
              <div>
                <h4 class="text-sm font-bold uppercase tracking-widest text-neutral-500 mb-3">Technologies</h4>
                <div class="flex flex-wrap gap-2">
                  <span v-for="tech in project.tech" :key="tech" class="text-xs bg-neutral-800 px-3 py-1 rounded-lg border border-neutral-700">
                    {{ tech }}
                  </span>
                </div>
              </div>

              <div class="flex gap-4 pt-4">
                <a href="#" class="flex-1 flex items-center justify-center gap-2 bg-white text-black font-bold py-3 rounded-xl hover:bg-purple-500 hover:text-white transition-all">
                  <ExternalLink :size="18" />
                  <span>Demo</span>
                </a>
                <a href="https://github.com/luisgantar1" target="_blank" class="flex-1 flex items-center justify-center gap-2 bg-neutral-800 font-bold py-3 rounded-xl hover:bg-neutral-700 transition-all">
                  <Github :size="18" />
                  <span>Code</span>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </Transition>
</template>
