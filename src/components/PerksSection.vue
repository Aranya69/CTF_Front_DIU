<template>
  <div class="relative">
    <div class="absolute inset-0 bg-cyber-red/5 blur-2xl"></div>
    <div class="relative bg-black/50 border border-cyber-red/30 rounded-lg p-8 sm:p-10 backdrop-blur-sm">
      <div class="flex flex-col sm:flex-row sm:flex-wrap justify-center items-center gap-6 sm:gap-8 md:gap-12">
        <div class="flex items-center gap-3">
          <svg class="w-8 h-8 text-cyber-red" fill="currentColor" viewBox="0 0 24 24">
            <path d="M16 21V5C16 3.89543 15.1046 3 14 3H10C8.89543 3 8 3.89543 8 5V21L12 19L16 21Z"/>
          </svg>
          <span class="text-gray-300 text-base uppercase tracking-wider">T-shirts</span>
        </div>

        <div class="text-cyber-red text-2xl">•</div>

        <div class="flex items-center gap-3">
          <svg class="w-8 h-8 text-cyber-red" fill="currentColor" viewBox="0 0 24 24">
            <path d="M12 2C6.48 2 2 6.48 2 12C2 17.52 6.48 22 12 22C17.52 22 22 17.52 22 12C22 6.48 17.52 2 12 2Z"/>
          </svg>
          <span class="text-gray-300 text-base uppercase tracking-wider">Snacks</span>
        </div>

        <div class="text-cyber-red text-2xl">•</div>

        <div class="flex items-center gap-3">
          <svg class="w-8 h-8 text-cyber-red" fill="currentColor" viewBox="0 0 24 24">
            <path d="M14 2H6C4.9 2 4 2.9 4 4V20C4 21.1 4.9 22 6 22H18C19.1 22 20 21.1 20 20V8L14 2Z"/>
          </svg>
          <span class="text-gray-300 text-base uppercase tracking-wider">Certificates</span>
        </div>
      </div>
      <p class="text-sm text-gray-400 text-center mt-6 uppercase tracking-widest">
        For All Participants
      </p>
    </div>
  </div>
</template>