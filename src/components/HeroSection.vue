<script setup>
const props = defineProps({
  scrollToSection: Function
})
</script>

<template>
  <section class="relative min-h-screen flex items-center justify-center bg-gradient-to-br from-black to-cyber-dark overflow-hidden pt-24 sm:pt-20 md:pt-0">
    <div class="absolute inset-0 opacity-20 sm:opacity-30 animate-pulse"
         style="background-image: linear-gradient(rgba(255,0,0,0.1) 1px, transparent 1px), linear-gradient(90deg, rgba(255,0,0,0.1) 1px, transparent 1px); background-size: 20px 20px;"></div>

    <div class="relative z-10 text-center px-4 py-8 sm:px-6">
      <p class="text-xs sm:text-sm md:text-base lg:text-lg text-cyber-red uppercase tracking-[0.2em] sm:tracking-[0.3em] mb-2 sm:mb-3">
        Capture the Flag 2025
      </p>
      <h1 class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl xl:text-8xl font-bold text-white mb-3 sm:mb-4 drop-shadow-[0_0_30px_rgba(255,0,0,1)] tracking-wider leading-tight">
        CSC_CYBERWAR
      </h1>
      <p class="text-sm sm:text-base md:text-lg text-gray-400 mb-8 sm:mb-12 tracking-widest">
        CSAD 2025
      </p>

      <div class="flex flex-col sm:flex-row gap-4 sm:gap-6 justify-center items-stretch sm:items-center max-w-md sm:max-w-none mx-auto">
        <button class="border-2 border-cyber-red text-cyber-red px-8 sm:px-10 md:px-12 py-4 text-base sm:text-lg md:text-xl uppercase tracking-widest hover:bg-cyber-red hover:text-black hover:shadow-[0_0_40px_rgba(255,0,0,0.8)] transition-all">
          Join the Battle
        </button>
        <button @click="scrollToSection('rules')"
                class="border-2 border-gray-400 text-gray-300 px-8 sm:px-10 md:px-12 py-4 text-base sm:text-lg md:text-xl uppercase tracking-widest hover:bg-gray-400 hover:text-black hover:shadow-[0_0_40px_rgba(156,163,175,0.8)] transition-all">
          Read Rules
        </button>
      </div>
    </div>

    <!-- Scroll Navigation -->
    <div class="absolute bottom-6 sm:bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
      <button @click="scrollToSection('bounty')" class="flex flex-col items-center gap-2 text-cyber-red hover:text-white transition-colors">
        <span class="text-xs uppercase tracking-widest">Scroll Down</span>
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
        </svg>
      </button>
    </div>
  </section>
</template>