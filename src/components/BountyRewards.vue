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
  <section id="bounty" class="min-h-screen py-16 sm:py-20 md:py-24 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-cyber-dark to-black">
    <div class="max-w-7xl mx-auto">
      <h2 class="text-3xl sm:text-4xl md:text-5xl text-cyber-red text-center mb-3 drop-shadow-[0_0_10px_rgba(255,0,0,1)] uppercase tracking-wider">
        Bounty Rewards
      </h2>
      <div class="h-1 w-24 sm:w-32 bg-cyber-red mx-auto mb-12 sm:mb-16 shadow-[0_0_10px_rgba(255,0,0,0.8)]"></div>

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