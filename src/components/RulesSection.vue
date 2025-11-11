<script setup>
import RuleCard from './RuleCard.vue'

const rules = [
  {
    title: 'Team Composition',
    icon: 'users',
    items: [
      'Each team must consist of <span class="text-white font-bold">3 members</span>',
      'One member designated as <span class="text-white font-bold">Team Leader</span>',
      '<span class="text-white font-bold">No substitutions</span> after registration closes'
    ]
  },
  {
    title: 'Competition Format',
    icon: 'gamepad',
    items: [
      '<span class="text-white font-bold">Jeopardy-style CTF</span> (points-based challenges)',
      'Categories: <span class="text-white font-bold">Web, Crypto, Forensics, Reverse Engineering, OSINT</span>',
      'Submit <span class="text-white font-bold">flags</span> to earn points based on difficulty'
    ]
  },
  {
    title: 'Rules of Conduct',
    icon: 'shield',
    items: [
      'No attacks on <span class="text-white font-bold">CTF infrastructure</span> or other teams',
      'No <span class="text-white font-bold">DoS, brute force</span>, or malicious behavior',
      'No <span class="text-white font-bold">sharing flags</span> or solutions during the event',
      '<span class="text-white font-bold">AI tools</span> and public scripts allowed within fair play'
    ]
  },
  {
    title: 'Disqualification Criteria',
    icon: 'warning',
    items: [
      '<span class="text-white font-bold">Sharing answers</span> or flags',
      '<span class="text-white font-bold">Tampering</span> with event systems',
      '<span class="text-white font-bold">Unauthorized access</span> or unfair advantage',
      '<span class="text-white font-bold">Disrupting</span> other teams or the environment'
    ]
  }
]

const additionalInfo = [
  'Challenges hosted on <span class="text-white font-bold">secure online platform</span>',
  '<span class="text-white font-bold">Bring your own laptop</span>',
  '<span class="text-white font-bold">External collaboration</span> between teams not allowed',
  '<span class="text-white font-bold">Judges\' decision is final</span> in all matters',
  'Uphold <span class="text-white font-bold">professional ethics and respect</span> throughout'
]
</script>

<template>
  <section id="rules" class="min-h-screen py-16 sm:py-20 md:py-24 px-4 sm:px-6 lg:px-8 bg-cyber-dark/30">
    <div class="max-w-6xl mx-auto">
      <h2 class="text-3xl sm:text-4xl md:text-5xl text-cyber-red text-center mb-3 drop-shadow-[0_0_10px_rgba(255,0,0,1)] uppercase tracking-wider">
        Rules & Guidelines
      </h2>
      <div class="h-1 w-24 sm:w-32 bg-cyber-red mx-auto mb-12 sm:mb-16 shadow-[0_0_10px_rgba(255,0,0,0.8)]"></div>

      <!-- Rules Grid -->
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-6 sm:gap-8 mb-16 sm:mb-20">
        <RuleCard
          v-for="rule in rules"
          :key="rule.title"
          :title="rule.title"
          :icon="rule.icon"
          :items="rule.items"
        />
      </div>

      <!-- Additional Info -->
      <div class="relative">
        <div class="absolute inset-0 bg-cyber-red/5 blur-2xl"></div>
        <div class="relative bg-black/50 border border-cyber-red/30 rounded-lg p-8 sm:p-10 backdrop-blur-sm">
          <h3 class="text-xl sm:text-2xl text-cyber-red uppercase tracking-wider font-bold mb-6 text-center">
            Additional Information
          </h3>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 text-base text-gray-300">
            <div v-for="(info, index) in additionalInfo" :key="index"
                 class="flex items-start gap-2"
                 :class="{ 'sm:col-span-2': index === additionalInfo.length - 1 }">
              <span class="text-cyber-red mt-1">•</span>
              <span v-html="info"></span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>