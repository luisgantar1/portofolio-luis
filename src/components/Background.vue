<template>
  <div class="fixed inset-0 -z-10 overflow-hidden pointer-events-none">
    <!-- Base Background -->
    <div class="absolute inset-0 bg-[#0a0a0a]"></div>

    <!-- Animated Gradients/Orbs -->
    <div 
      class="absolute top-[-5%] left-[-5%] w-[50%] h-[50%] bg-purple-600/20 rounded-full blur-[120px] animate-pulse"
      style="animation-duration: 8s;"
    ></div>
    <div 
      class="absolute bottom-[5%] right-[-5%] w-[45%] h-[45%] bg-blue-600/15 rounded-full blur-[120px] animate-pulse"
      style="animation-duration: 12s;"
    ></div>

    <!-- Grid Overlay -->
    <div 
      class="absolute inset-0 opacity-[0.25]" 
      style="background-image: radial-gradient(#333 1px, transparent 1px); background-size: 50px 50px;"
    ></div>

    <!-- Moving Lines (Data vibe) -->
    <div class="absolute inset-0 opacity-[0.1]">
      <div 
        v-for="i in 3" 
        :key="i"
        class="absolute bg-gradient-to-r from-transparent via-purple-400 to-transparent h-[2px] w-full"
        :style="{
          top: `${i * 30}%`,
          left: '-100%',
          animation: `scanline ${8 + i * 2}s linear infinite`,
          animationDelay: `${i * 2}s`
        }"
      ></div>
    </div>
  </div>
</template>

<style scoped>
@keyframes scanline {
  0% { transform: translateX(0); }
  100% { transform: translateX(200%); }
}

@keyframes pulse {
  0%, 100% { opacity: 0.1; transform: scale(1); }
  50% { opacity: 0.2; transform: scale(1.1); }
}
</style>
