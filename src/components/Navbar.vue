<script setup>
import { ref } from "vue";

const props = defineProps({
  scrollToSection: Function,
});

const mobileMenuOpen = ref(false);

const handleNavClick = (sectionId) => {
  props.scrollToSection(sectionId);
  mobileMenuOpen.value = false;
};
</script>

<template>
  <nav
    class="fixed top-0 w-full bg-gradient-to-r from-black via-darker-bg to-black backdrop-blur-lg border-b-2 border-cyber-red z-50 relative overflow-hidden"
  >
    <!-- Animated background pattern -->
    <div
      class="absolute inset-0 opacity-5"
      style="
        background-image: linear-gradient(
          90deg,
          rgba(0, 255, 65, 0.1) 1px,
          transparent 1px
        );
        background-size: 20px 20px;
      "
    ></div>

    <!-- Scan line effect -->
    <div
      class="absolute top-0 left-0 w-full h-0.5 bg-gradient-to-r from-transparent via-cyber-green to-transparent opacity-50"
    ></div>
    <div
      class="absolute bottom-0 left-0 w-full h-0.5 bg-gradient-to-r from-transparent via-cyber-red to-transparent opacity-50"
    ></div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-3 sm:py-4 relative">
      <div class="flex justify-between items-center">
        <div class="flex-shrink-0 group">
          <div class="relative">
            <img
              src="../assets/logo.png"
              alt="Cyber Security Center"
              class="h-10 sm:h-12 md:h-16 w-auto transition-all duration-500 group-hover:scale-110"
              style="
                filter: drop-shadow(0 0 10px rgba(255, 0, 0, 0.5))
                  drop-shadow(0 0 5px rgba(0, 255, 65, 0.3));
              "
            />
            <!-- Logo brackets -->
            <span
              class="absolute -left-3 top-1/2 -translate-y-1/2 text-cyber-green font-mono text-xl opacity-0 group-hover:opacity-100 transition-opacity"
              >&lt;</span
            >
            <span
              class="absolute -right-3 top-1/2 -translate-y-1/2 text-cyber-green font-mono text-xl opacity-0 group-hover:opacity-100 transition-opacity"
              >/&gt;</span
            >
          </div>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center gap-4 md:gap-8">
          <button
            @click="handleNavClick('bounty')"
            class="relative text-cyber-red uppercase tracking-widest text-sm hover:text-cyber-green transition-all duration-300 font-mono group"
          >
            <span class="relative z-10">&lt; Rewards /&gt;</span>
            <span
              class="absolute inset-0 bg-cyber-red/10 scale-x-0 group-hover:scale-x-100 transition-transform origin-left"
            ></span>
            <span
              class="absolute bottom-0 left-0 w-0 h-0.5 bg-cyber-green group-hover:w-full transition-all duration-300"
            ></span>
          </button>
          <button
            @click="handleNavClick('rules')"
            class="relative text-cyber-red uppercase tracking-widest text-sm hover:text-cyber-blue transition-all duration-300 font-mono group"
          >
            <span class="relative z-10">&lt; Rules /&gt;</span>
            <span
              class="absolute inset-0 bg-cyber-blue/10 scale-x-0 group-hover:scale-x-100 transition-transform origin-left"
            ></span>
            <span
              class="absolute bottom-0 left-0 w-0 h-0.5 bg-cyber-blue group-hover:w-full transition-all duration-300"
            ></span>
          </button>
          <button
            class="relative group bg-gradient-to-r from-cyber-red via-red-700 to-cyber-red text-white border-2 border-cyber-red px-6 md:px-8 py-2 md:py-3 uppercase tracking-widest text-sm md:text-base overflow-hidden animate-pulse-glow font-mono"
          >
            <a href="http://localhost:8000/register">
              <span class="relative z-10 flex items-center gap-2">
                <span>&gt;&gt;</span>
                Register
                <span>&lt;&lt;</span>
              </span>
              <div
                class="absolute inset-0 bg-gradient-to-r from-cyber-green to-cyber-blue opacity-0 group-hover:opacity-100 transition-opacity"
              ></div>
            </a>
          </button>
        </div>

        <!-- Mobile Menu Button -->
        <button
          @click="mobileMenuOpen = !mobileMenuOpen"
          class="md:hidden flex flex-col gap-1.5 p-2 relative group"
        >
          <span
            class="w-6 h-0.5 bg-cyber-red group-hover:bg-cyber-green transition-all duration-300"
            :class="mobileMenuOpen ? 'rotate-45 translate-y-2' : ''"
            style="box-shadow: 0 0 5px currentColor"
          ></span>
          <span
            class="w-6 h-0.5 bg-cyber-red group-hover:bg-cyber-green transition-all duration-300"
            :class="mobileMenuOpen ? 'opacity-0' : ''"
            style="box-shadow: 0 0 5px currentColor"
          ></span>
          <span
            class="w-6 h-0.5 bg-cyber-red group-hover:bg-cyber-green transition-all duration-300"
            :class="mobileMenuOpen ? '-rotate-45 -translate-y-2' : ''"
            style="box-shadow: 0 0 5px currentColor"
          ></span>
        </button>
      </div>

      <!-- Mobile Menu -->
      <div
        v-show="mobileMenuOpen"
        class="md:hidden absolute top-full left-0 w-full bg-gradient-to-br from-black via-darker-bg to-black backdrop-blur-lg border-b-2 border-cyber-red/50 py-4 animate-slide-down"
      >
        <div class="flex flex-col gap-3 px-4">
          <button
            @click="handleNavClick('bounty')"
            class="relative text-cyber-red uppercase tracking-widest text-sm hover:text-cyber-green hover:bg-cyber-red/10 py-3 transition-all text-left font-mono group overflow-hidden border border-transparent hover:border-cyber-green/30"
          >
            <span class="relative z-10">&gt; Rewards_</span>
            <div
              class="absolute inset-0 bg-gradient-to-r from-cyber-red/5 to-transparent translate-x-full group-hover:translate-x-0 transition-transform"
            ></div>
          </button>
          <button
            @click="handleNavClick('rules')"
            class="relative text-cyber-red uppercase tracking-widest text-sm hover:text-cyber-blue hover:bg-cyber-red/10 py-3 transition-all text-left font-mono group overflow-hidden border border-transparent hover:border-cyber-blue/30"
          >
            <span class="relative z-10">&gt; Rules_</span>
            <div
              class="absolute inset-0 bg-gradient-to-r from-cyber-blue/5 to-transparent translate-x-full group-hover:translate-x-0 transition-transform"
            ></div>
          </button>
          <button
            class="relative bg-gradient-to-r from-cyber-red to-red-700 text-white border-2 border-cyber-red px-6 py-3 uppercase tracking-widest text-sm animate-pulse-glow font-mono overflow-hidden group"
          >
            <span class="relative z-10">&gt;&gt; Register Now</span>
            <div
              class="absolute inset-0 bg-cyber-green opacity-0 group-hover:opacity-20 transition-opacity"
            ></div>
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped>
@keyframes slide-down {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-slide-down {
  animation: slide-down 0.3s ease-out;
}
</style>
