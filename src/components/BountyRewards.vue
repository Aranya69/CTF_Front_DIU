<script setup>
import PrizeCard from './PrizeCard.vue'
import PerksSection from './PerksSection.vue'

const prizes = [
  { place: '1st', amount: '10,000', color: 'red', rank: 1 },
  { place: '2nd', amount: '6,000', color: 'silver', rank: 2 },
  { place: '3rd', amount: '4,000', color: 'bronze', rank: 3 }
]
</script>

<template>
  <section id="bounty" class="relative min-h-screen py-16 sm:py-20 md:py-24 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-cyber-dark via-black to-darker-bg overflow-hidden">
    <!-- Hexagon Pattern Background -->
    <div class="absolute inset-0 opacity-5"
         style="background-image: url('data:image/svg+xml,%3Csvg width=&quot;100&quot; height=&quot;100&quot; xmlns=&quot;http://www.w3.org/2000/svg&quot;%3E%3Cpath d=&quot;M50 0L93.3 25v50L50 100 6.7 75V25z&quot; fill=&quot;none&quot; stroke=&quot;%2300ff41&quot; stroke-width=&quot;1&quot;/%3E%3C/svg%3E'); background-size: 100px 100px;"></div>

    <!-- Animated particles -->
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
      <div class="absolute w-2 h-2 bg-cyber-red rounded-full animate-float opacity-30" style="top: 20%; left: 10%;"></div>
      <div class="absolute w-2 h-2 bg-cyber-green rounded-full animate-float opacity-30" style="top: 40%; right: 15%; animation-delay: 1s;"></div>
      <div class="absolute w-2 h-2 bg-cyber-blue rounded-full animate-float opacity-30" style="top: 60%; left: 20%; animation-delay: 2s;"></div>
      <div class="absolute w-2 h-2 bg-cyber-purple rounded-full animate-float opacity-30" style="top: 80%; right: 25%; animation-delay: 1.5s;"></div>
    </div>

    <div class="max-w-7xl mx-auto relative">
      <!-- Title with glitch effect -->
      <div class="text-center mb-12 sm:mb-16">
        <p class="text-cyber-green text-sm sm:text-base font-mono mb-2">&lt;section id=&quot;bounty&quot;&gt;</p>
        <div class="relative inline-block">
          <h2 class="text-3xl sm:text-4xl md:text-5xl text-cyber-red text-center mb-3 uppercase tracking-wider font-mono relative z-10"
              style="text-shadow: 0 0 10px rgba(255,0,0,0.8), 0 0 20px rgba(255,0,0,0.5), 2px 2px 0px rgba(0,255,65,0.3);">
            &lt; Bounty_Rewards /&gt;
          </h2>
        </div>
        <div class="relative h-1 w-24 sm:w-32 mx-auto mb-2">
          <div class="absolute inset-0 bg-gradient-to-r from-transparent via-cyber-red to-transparent shadow-[0_0_10px_rgba(255,0,0,0.8)] animate-pulse"></div>
          <div class="absolute inset-0 bg-gradient-to-r from-cyber-green via-cyber-blue to-cyber-red opacity-50 animate-pulse" style="animation-delay: 0.5s;"></div>
        </div>
        <p class="text-cyber-green text-sm sm:text-base font-mono">&lt;/section&gt;</p>
      </div>

      <!-- Prize Cards -->
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6 sm:gap-8 mb-16 sm:mb-20">
        <PrizeCard
          v-for="prize in prizes"
          :key="prize.rank"
          :place="prize.place"
          :amount="prize.amount"
          :color="prize.color"
          :rank="prize.rank"
        />
      </div>

      <PerksSection />
    </div>
  </section>
</template>