<template>
  <div class="max-w-3xl mb-16">
    <h1 
      v-motion
      :initial="{ opacity: 0, y: 50 }"
      :enter="{ opacity: 1, y: 0, transition: { delay: 200 } }"
      class="text-5xl md:text-7xl font-bold mb-6 leading-tight"
    >
      Bridging <span class="text-purple-500">Intelligence</span> with <span class="text-neutral-500">Interfaces.</span>
    </h1>
    <p 
      v-motion
      :initial="{ opacity: 0, y: 20 }"
      :enter="{ opacity: 1, y: 0, transition: { delay: 400 } }"
      class="text-neutral-400 text-lg md:text-xl leading-relaxed mb-8"
    >
      Halo, saya Luis. Seorang developer yang memiliki minat besar dalam dunia <b>Machine Learning</b> dan <b>Web Development</b>. Saya senang mengeksplorasi kecerdasan buatan sekaligus membangun aplikasi web yang modern, responsif, dan fungsional.
    </p>
    <div 
      v-motion
      :initial="{ opacity: 0 }"
      :enter="{ opacity: 1, transition: { delay: 600 } }"
      class="flex gap-4"
    >
      <a href="#projects" class="bg-white text-black px-6 py-3 rounded-full font-bold hover:bg-purple-500 hover:text-white transition-all">Lihat Proyek</a>
      <a href="#contact" class="border border-neutral-800 px-6 py-3 rounded-full font-bold hover:bg-neutral-900 transition-all">Kontak Saya</a>
    </div>
  </div>
</template>
