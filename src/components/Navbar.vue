<script setup>
import { ref } from 'vue'

const props = defineProps({
  scrollToSection: Function
})

const mobileMenuOpen = ref(false)

const handleNavClick = (sectionId) => {
  props.scrollToSection(sectionId)
  mobileMenuOpen.value = false
}
</script>

<template>
  <nav class="fixed top-0 w-full bg-black/90 backdrop-blur-lg border-b-2 border-cyber-red z-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-3 sm:py-4">
      <div class="flex justify-between items-center">
        <div class="flex-shrink-0">
          <img src="../assets/logo.png" alt="Cyber Security Center"
               class="h-10 sm:h-12 md:h-16 w-auto drop-shadow-[0_0_10px_rgba(255,0,0,0.5)]" />
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center gap-4 md:gap-8">
          <button @click="handleNavClick('bounty')"
                  class="text-cyber-red uppercase tracking-widest text-sm hover:text-white hover:drop-shadow-[0_0_10px_rgba(255,0,0,1)] transition-all">
            Rewards
          </button>
          <button @click="handleNavClick('rules')"
                  class="text-cyber-red uppercase tracking-widest text-sm hover:text-white hover:drop-shadow-[0_0_10px_rgba(255,0,0,1)] transition-all">
            Rules
          </button>
          <button class="bg-gradient-to-r from-cyber-red to-red-700 text-white border-2 border-cyber-red px-6 md:px-8 py-2 md:py-3 uppercase tracking-widest text-sm md:text-base shadow-[0_0_20px_rgba(255,0,0,0.5)] hover:shadow-[0_0_30px_rgba(255,0,0,0.8)] hover:-translate-y-1 transition-all">
            Register
          </button>
        </div>

        <!-- Mobile Menu Button -->
        <button @click="mobileMenuOpen = !mobileMenuOpen"
                class="md:hidden flex flex-col gap-1.5 p-2">
          <span class="w-6 h-0.5 bg-cyber-red transition-all"
                :class="mobileMenuOpen ? 'rotate-45 translate-y-2' : ''"></span>
          <span class="w-6 h-0.5 bg-cyber-red transition-all"
                :class="mobileMenuOpen ? 'opacity-0' : ''"></span>
          <span class="w-6 h-0.5 bg-cyber-red transition-all"
                :class="mobileMenuOpen ? '-rotate-45 -translate-y-2' : ''"></span>
        </button>
      </div>

      <!-- Mobile Menu -->
      <div v-show="mobileMenuOpen"
           class="md:hidden absolute top-full left-0 w-full bg-black/95 backdrop-blur-lg border-b-2 border-cyber-red/50 py-4">
        <div class="flex flex-col gap-3 px-4">
          <button @click="handleNavClick('bounty')"
                  class="text-cyber-red uppercase tracking-widest text-sm hover:text-white hover:bg-cyber-red/10 py-3 transition-all text-left">
            Rewards
          </button>
          <button @click="handleNavClick('rules')"
                  class="text-cyber-red uppercase tracking-widest text-sm hover:text-white hover:bg-cyber-red/10 py-3 transition-all text-left">
            Rules
          </button>
          <button class="bg-gradient-to-r from-cyber-red to-red-700 text-white border-2 border-cyber-red px-6 py-3 uppercase tracking-widest text-sm shadow-[0_0_20px_rgba(255,0,0,0.5)] transition-all">
            Register Now
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>