<script setup>
const props = defineProps({
  title: String,
  icon: String,
  items: Array
})

const iconPaths = {
  // Team icon - multiple hackers/users with terminal theme
  users: 'M8 7a4 4 0 100-8 4 4 0 000 8zM6 9h4a6 6 0 016 6v3H0v-3a6 6 0 016-6zm10-2a4 4 0 100-8 4 4 0 000 8zm0 2h4a6 6 0 016 6v3h-6v-3a7.97 7.97 0 00-1.64-4.85A6.97 6.97 0 0116 9z',
  // Game controller/CTF challenges icon
  gamepad: 'M3 5h2v2H3V5zm0 4h2v2H3V9zm4-4h2v2H7V5zm0 4h2v2H7V9zm4-4h2v2h-2V5zm0 4h2v2h-2V9zm4-4h2v2h-2V5zm0 4h2v2h-2V9zm4-4h2v2h-2V5zm0 4h2v2h-2V9zm-8 4h2v2h-2v-2zm-4 0h2v2H7v-2zm8 0h2v2h-2v-2zm4 0h2v2h-2v-2zm-8 4h2v2h-2v-2zm4 0h2v2h-2v-2z',
  // Shield with lock - security rules
  shield: 'M12 1L3 5v6c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V5l-9-4zm0 10.99h7c-.53 4.12-3.28 7.79-7 8.94V12H5V6.3l7-3.11v8.8z M12 7c-1.1 0-2 .9-2 2v1h4V9c0-1.1-.9-2-2-2zm0 1c.55 0 1 .45 1 1v1h-2V9c0-.55.45-1 1-1z',
  // Skull/warning - disqualification theme
  warning: 'M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zM11 7h2v6h-2zm0 8h2v2h-2z'
}
</script>

<template>
  <div class="relative group h-full" style="perspective: 1000px;">
    <div class="absolute inset-0 bg-gradient-to-br from-cyber-red/10 via-cyber-blue/10 to-cyber-green/10 blur-lg opacity-50 group-hover:opacity-100 transition-all duration-500"></div>
    <div class="relative bg-gradient-to-br from-black via-darker-bg to-black border-2 border-cyber-red/50 p-6 sm:p-8 hover:border-cyber-red transition-all duration-500 transform hover:-translate-y-2 hover:scale-[1.02] h-full flex flex-col"
         style="transform-style: preserve-3d;">

      <!-- Corner Brackets -->
      <div class="absolute top-2 left-2 text-cyber-green font-mono text-xl opacity-50 group-hover:opacity-100 transition-opacity">[</div>
      <div class="absolute top-2 right-2 text-cyber-green font-mono text-xl opacity-50 group-hover:opacity-100 transition-opacity">]</div>
      <div class="absolute bottom-2 left-2 text-cyber-green font-mono text-xl opacity-50 group-hover:opacity-100 transition-opacity">[</div>
      <div class="absolute bottom-2 right-2 text-cyber-green font-mono text-xl opacity-50 group-hover:opacity-100 transition-opacity">]</div>

      <!-- Animated Corner Lines -->
      <div class="absolute top-0 left-0 w-8 h-0.5 bg-cyber-blue transition-all duration-500 group-hover:w-16"></div>
      <div class="absolute top-0 left-0 w-0.5 h-8 bg-cyber-blue transition-all duration-500 group-hover:h-16"></div>
      <div class="absolute top-0 right-0 w-8 h-0.5 bg-cyber-blue transition-all duration-500 group-hover:w-16"></div>
      <div class="absolute top-0 right-0 w-0.5 h-8 bg-cyber-blue transition-all duration-500 group-hover:h-16"></div>

      <div class="flex items-start gap-4 mb-4">
        <div class="relative">
          <svg class="w-8 h-8 text-cyber-red flex-shrink-0 mt-1 transition-all duration-500 group-hover:scale-110 group-hover:rotate-12 group-hover:text-cyber-blue"
               style="filter: drop-shadow(0 0 10px currentColor);"
               fill="currentColor" viewBox="0 0 24 24">
            <path :d="iconPaths[icon]"/>
          </svg>
          <!-- Icon glow effect -->
          <div class="absolute inset-0 blur-md bg-cyber-red opacity-0 group-hover:opacity-50 transition-opacity"></div>
        </div>
        <h3 class="text-xl sm:text-2xl text-cyber-red uppercase tracking-wider font-bold font-mono group-hover:text-cyber-blue transition-colors duration-300"
            style="text-shadow: 0 0 10px rgba(255,0,0,0.5);">
          &lt; {{ title }} /&gt;
        </h3>
      </div>

      <ul class="space-y-3 text-gray-300 text-base sm:text-lg flex-grow">
        <li v-for="(item, index) in items" :key="index"
            class="flex items-start gap-3 group/item hover:translate-x-2 transition-transform duration-300">
          <span class="text-cyber-green mt-1 font-mono font-bold group-hover/item:text-cyber-blue transition-colors">&gt;&gt;</span>
          <span class="group-hover/item:text-white transition-colors" v-html="item"></span>
        </li>
      </ul>

      <!-- Scan line animation -->
      <div class="absolute inset-0 pointer-events-none overflow-hidden opacity-0 group-hover:opacity-30 transition-opacity">
        <div class="h-px w-full bg-gradient-to-r from-transparent via-cyber-blue to-transparent animate-scan"></div>
      </div>
    </div>
  </div>
</template>
