<template>
  <div class="relative group">
    <div class="absolute inset-0 bg-gradient-to-br from-cyber-red/10 via-cyber-green/10 to-cyber-blue/10 blur-2xl"></div>
    <div class="relative bg-gradient-to-br from-black/70 via-darker-bg/70 to-black/70 border-2 border-cyber-green/50 p-10 sm:p-12 backdrop-blur-sm group-hover:border-cyber-blue transition-all duration-500"
         style="box-shadow: 0 0 20px rgba(0,255,65,0.2);">

      <!-- Title -->
      <h3 class="text-2xl sm:text-3xl md:text-4xl text-cyber-green text-center mb-8 uppercase tracking-wider font-black font-mono"
          style="text-shadow: 0 0 15px rgba(0,255,65,0.8), 0 0 30px rgba(0,255,65,0.5);">
        &lt; Participant_Perks /&gt;
      </h3>

      <div class="flex flex-col sm:flex-row sm:flex-wrap justify-center items-center gap-8 sm:gap-10 md:gap-14">
        <div class="flex items-center gap-4 group/item hover:scale-110 transition-transform duration-300">
          <svg class="w-12 h-12 sm:w-14 sm:h-14 text-cyber-red group-hover/item:text-cyber-green transition-colors"
               fill="currentColor" viewBox="0 0 24 24"
               style="filter: drop-shadow(0 0 10px currentColor);">
            <path d="M16 21V5C16 3.89543 15.1046 3 14 3H10C8.89543 3 8 5V21L12 19L16 21Z"/>
          </svg>
          <span class="text-white text-lg sm:text-xl md:text-2xl uppercase tracking-wider font-bold font-mono"
                style="text-shadow: 0 0 8px rgba(255,255,255,0.5);">T-shirts</span>
        </div>

        <div class="text-cyber-green text-3xl sm:text-4xl animate-pulse"
             style="text-shadow: 0 0 15px currentColor;">•</div>

        <div class="flex items-center gap-4 group/item hover:scale-110 transition-transform duration-300">
          <svg class="w-12 h-12 sm:w-14 sm:h-14 text-cyber-blue group-hover/item:text-cyber-purple transition-colors"
               fill="currentColor" viewBox="0 0 24 24"
               style="filter: drop-shadow(0 0 10px currentColor);">
            <path d="M12 2C6.48 2 2 6.48 2 12C2 17.52 6.48 22 12 22C17.52 22 22 17.52 22 12C22 6.48 17.52 2 12 2Z"/>
          </svg>
          <span class="text-white text-lg sm:text-xl md:text-2xl uppercase tracking-wider font-bold font-mono"
                style="text-shadow: 0 0 8px rgba(255,255,255,0.5);">Snacks</span>
        </div>

        <div class="text-cyber-blue text-3xl sm:text-4xl animate-pulse" style="animation-delay: 0.3s; text-shadow: 0 0 15px currentColor;">•</div>

        <div class="flex items-center gap-4 group/item hover:scale-110 transition-transform duration-300">
          <svg class="w-12 h-12 sm:w-14 sm:h-14 text-cyber-purple group-hover/item:text-cyber-red transition-colors"
               fill="currentColor" viewBox="0 0 24 24"
               style="filter: drop-shadow(0 0 10px currentColor);">
            <path d="M14 2H6C4.9 2 4 2.9 4 4V20C4 21.1 4.9 22 6 22H18C19.1 22 20 21.1 20 20V8L14 2Z"/>
          </svg>
          <span class="text-white text-lg sm:text-xl md:text-2xl uppercase tracking-wider font-bold font-mono"
                style="text-shadow: 0 0 8px rgba(255,255,255,0.5);">Certificates</span>
        </div>
      </div>

      <div class="mt-8 pt-6 border-t border-cyber-green/30">
        <p class="text-base sm:text-lg md:text-xl text-cyber-blue text-center uppercase tracking-widest font-bold font-mono"
           style="text-shadow: 0 0 10px rgba(0,217,255,0.8);">
          [ For_All_Participants ]
        </p>
      </div>
    </div>
  </div>
</template>
