<template>
  <footer class="relative border-t-2 border-cyber-red/30 bg-gradient-to-b from-black via-darker-bg to-black py-8 px-4 overflow-hidden">
    <!-- Binary rain background -->
    <div class="absolute inset-0 opacity-5 font-mono text-xs text-cyber-green"
         style="background: repeating-linear-gradient(0deg, transparent, transparent 20px, rgba(0,255,65,0.1) 20px, rgba(0,255,65,0.1) 21px);">
    </div>

    <!-- Top gradient line -->
    <div class="absolute top-0 left-0 w-full h-0.5">
      <div class="h-full bg-gradient-to-r from-transparent via-cyber-red to-transparent animate-pulse"></div>
      <div class="h-full bg-gradient-to-r from-cyber-green via-cyber-blue to-cyber-purple opacity-50" style="animation: scan 3s linear infinite;"></div>
    </div>

    <div class="max-w-7xl mx-auto relative">
      <div class="flex flex-col items-center gap-4">
        <!-- Decorative code comment -->
 

        <div class="flex flex-col items-center gap-3 group">
          <p class="text-base sm:text-lg md:text-xl text-gray-400 text-center font-mono group-hover:text-gray-300 transition-colors">
            <span class="text-cyber-green">&gt;</span>
            © 2025
            <span class="text-cyber-red group-hover:text-cyber-green transition-colors">CSC_Cyber_Security_Centre</span>
            <span class="text-gray-500">|</span>
            <span class="text-white font-bold group-hover:text-cyber-blue transition-colors">CSAD_CYBERWAR</span>
            <span class="text-cyber-green">&lt;</span>
          </p>

          <!-- Animated divider -->
          <div class="h-px w-32 bg-gradient-to-r from-transparent via-cyber-red to-transparent opacity-30 group-hover:opacity-60 transition-opacity"></div>

          <p class="text-sm sm:text-base text-gray-500 uppercase tracking-widest text-center font-mono group-hover:text-cyber-green transition-colors">
            <span class="text-cyber-red group-hover:text-cyber-blue transition-colors animate-flicker">//</span>
            <span class="inline-block group-hover:scale-105 transition-transform">May_the_best_hackers_win</span>
            <span class="text-cyber-red group-hover:text-cyber-blue transition-colors animate-flicker">_</span>
          </p>
        </div>

        <!-- Binary decorations -->
        <div class="flex gap-2 text-xs sm:text-sm text-cyber-green/20 font-mono mt-2">
          <span>01001000</span>
          <span>01000001</span>
          <span>01000011</span>
          <span>01001011</span>
        </div>

       
      </div>
    </div>

    <!-- Bottom animated line -->
    <div class="absolute bottom-0 left-0 w-full h-px">
      <div class="h-full bg-gradient-to-r from-cyber-blue via-cyber-green to-cyber-red opacity-30 animate-pulse"></div>
    </div>
  </footer>
</template>