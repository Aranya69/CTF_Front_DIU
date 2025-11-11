<template>
  <section class="relative py-16 sm:py-20 md:py-24 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-black via-cyber-dark to-darker-bg overflow-hidden">
    <!-- Circuit board pattern -->
    <div class="absolute inset-0 opacity-10">
      <svg class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <pattern id="circuit" x="0" y="0" width="100" height="100" patternUnits="userSpaceOnUse">
            <circle cx="10" cy="10" r="2" fill="#00ff41"/>
            <line x1="10" y1="10" x2="50" y2="10" stroke="#00ff41" stroke-width="1"/>
            <line x1="50" y1="10" x2="50" y2="50" stroke="#ff0000" stroke-width="1"/>
            <circle cx="50" cy="50" r="2" fill="#ff0000"/>
            <line x1="50" y1="50" x2="90" y2="50" stroke="#00d9ff" stroke-width="1"/>
            <circle cx="90" cy="50" r="2" fill="#00d9ff"/>
          </pattern>
        </defs>
        <rect width="100%" height="100%" fill="url(#circuit)"/>
      </svg>
    </div>

    <div class="max-w-4xl mx-auto text-center relative">
      <div class="relative">
        <div class="absolute inset-0 bg-gradient-to-br from-cyber-red/20 via-cyber-blue/20 to-cyber-green/20 blur-3xl animate-pulse"></div>
        <div class="relative bg-gradient-to-br from-black/90 via-darker-bg/90 to-black/90 border-2 border-cyber-red/50 p-10 sm:p-14 md:p-16 backdrop-blur-sm overflow-hidden group"
             style="box-shadow: 0 0 30px rgba(255,0,0,0.3), inset 0 0 30px rgba(0,0,0,0.5);">

          <!-- Corner decorations -->
          <div class="absolute top-0 left-0 w-16 h-16 border-t-2 border-l-2 border-cyber-green opacity-50 group-hover:w-24 group-hover:h-24 transition-all duration-500"></div>
          <div class="absolute top-0 right-0 w-16 h-16 border-t-2 border-r-2 border-cyber-blue opacity-50 group-hover:w-24 group-hover:h-24 transition-all duration-500"></div>
          <div class="absolute bottom-0 left-0 w-16 h-16 border-b-2 border-l-2 border-cyber-blue opacity-50 group-hover:w-24 group-hover:h-24 transition-all duration-500"></div>
          <div class="absolute bottom-0 right-0 w-16 h-16 border-b-2 border-r-2 border-cyber-green opacity-50 group-hover:w-24 group-hover:h-24 transition-all duration-500"></div>

          <!-- Scan lines -->
          <div class="absolute inset-0 opacity-20 pointer-events-none">
            <div class="h-px w-full bg-gradient-to-r from-transparent via-cyber-blue to-transparent animate-scan"></div>
          </div>

          <div class="relative z-10">
            <div class="inline-block mb-4">
              <p class="text-cyber-green text-sm sm:text-base font-mono text-left">&gt; system.prompt()</p>
            </div>

            <h2 class="text-2xl sm:text-3xl md:text-4xl uppercase tracking-wider mb-6 font-mono"
                style="text-shadow: 0 0 20px rgba(255,0,0,0.5);">
              <span class="text-cyber-green animate-flicker">&gt;&gt;</span>
              <span class="text-white">Ready_to_</span>
              <span class="text-cyber-red animate-pulse">Hack</span>
              <span class="text-white">?</span>
              <span class="text-cyber-blue animate-flicker">&lt;&lt;</span>
            </h2>

            <p class="text-base sm:text-lg md:text-xl text-gray-300 mb-8 leading-relaxed max-w-2xl mx-auto font-mono">
              <span class="text-cyber-blue">[</span>
              Register your team now and prepare for the ultimate cybersecurity challenge.
              <span class="text-cyber-blue">]</span>
            </p>

            <button class="group/btn relative bg-gradient-to-r from-cyber-red via-red-700 to-cyber-red text-white border-2 border-cyber-red px-10 sm:px-14 md:px-16 py-4 sm:py-5 text-base sm:text-lg md:text-xl uppercase tracking-widest font-bold overflow-hidden animate-pulse-glow font-mono">
              <span class="relative z-10 flex items-center justify-center gap-3">
                <span class="text-cyber-green">&gt;&gt;</span>
                Start_Registration
                <span class="text-cyber-green">&lt;&lt;</span>
              </span>
              <div class="absolute inset-0 bg-gradient-to-r from-cyber-green via-cyber-blue to-cyber-purple opacity-0 group-hover/btn:opacity-100 transition-opacity duration-500"></div>

              <!-- Animated border -->
              <div class="absolute inset-0 opacity-0 group-hover/btn:opacity-100 transition-opacity">
                <div class="absolute top-0 left-0 w-full h-0.5 bg-gradient-to-r from-cyber-green to-cyber-blue animate-scan"></div>
                <div class="absolute bottom-0 left-0 w-full h-0.5 bg-gradient-to-r from-cyber-blue to-cyber-green animate-scan" style="animation-delay: 0.5s;"></div>
              </div>
            </button>

            <div class="inline-block mt-4">
              <p class="text-cyber-green text-sm sm:text-base font-mono text-left">&gt; end.prompt()</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>