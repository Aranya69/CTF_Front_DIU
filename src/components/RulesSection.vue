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
  <section id="rules" class="relative min-h-screen py-16 sm:py-20 md:py-24 px-4 sm:px-6 lg:px-8 bg-gradient-to-b from-darker-bg via-cyber-dark/30 to-black overflow-hidden">
    <!-- Circuit pattern background -->
    <div class="absolute inset-0 opacity-5"
         style="background-image: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,255,65,0.2) 2px, rgba(0,255,65,0.2) 4px), repeating-linear-gradient(90deg, transparent, transparent 2px, rgba(0,217,255,0.2) 2px, rgba(0,217,255,0.2) 4px); background-size: 50px 50px;"></div>

    <div class="max-w-6xl mx-auto relative">
      <!-- Title -->
      <div class="text-center mb-12 sm:mb-16">
        <p class="text-cyber-blue text-sm sm:text-base font-mono mb-2">&lt;section id=&quot;rules&quot;&gt;</p>
        <h2 class="text-3xl sm:text-4xl md:text-5xl text-cyber-red text-center mb-3 uppercase tracking-wider font-mono relative inline-block"
            style="text-shadow: 0 0 10px rgba(255,0,0,0.8), 0 0 20px rgba(255,0,0,0.5), 2px 2px 0px rgba(0,217,255,0.3);">
          &lt; Rules_&_Guidelines /&gt;
        </h2>
        <div class="relative h-1 w-24 sm:w-32 mx-auto mb-2">
          <div class="absolute inset-0 bg-gradient-to-r from-transparent via-cyber-red to-transparent shadow-[0_0_10px_rgba(255,0,0,0.8)] animate-pulse"></div>
          <div class="absolute inset-0 bg-gradient-to-r from-cyber-blue via-cyber-green to-cyber-red opacity-50 animate-pulse" style="animation-delay: 0.5s;"></div>
        </div>
        <p class="text-cyber-blue text-sm sm:text-base font-mono">&lt;/section&gt;</p>
      </div>

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
      <div class="relative group">
        <div class="absolute inset-0 bg-gradient-to-br from-cyber-blue/10 via-cyber-green/10 to-cyber-red/5 blur-2xl"></div>
        <div class="relative bg-gradient-to-br from-black/70 via-darker-bg/70 to-black/70 border-2 border-cyber-blue/50 p-8 sm:p-10 backdrop-blur-sm group-hover:border-cyber-green transition-all duration-500"
             style="box-shadow: 0 0 20px rgba(0,217,255,0.2);">

          <!-- Corner brackets -->
          <div class="absolute top-0 left-0 w-12 h-12 border-t-2 border-l-2 border-cyber-green opacity-40 group-hover:w-16 group-hover:h-16 transition-all"></div>
          <div class="absolute top-0 right-0 w-12 h-12 border-t-2 border-r-2 border-cyber-green opacity-40 group-hover:w-16 group-hover:h-16 transition-all"></div>
          <div class="absolute bottom-0 left-0 w-12 h-12 border-b-2 border-l-2 border-cyber-blue opacity-40 group-hover:w-16 group-hover:h-16 transition-all"></div>
          <div class="absolute bottom-0 right-0 w-12 h-12 border-b-2 border-r-2 border-cyber-blue opacity-40 group-hover:w-16 group-hover:h-16 transition-all"></div>

          <h3 class="text-2xl sm:text-3xl md:text-4xl text-cyber-blue uppercase tracking-wider font-black mb-8 text-center font-mono group-hover:text-cyber-green transition-colors"
              style="text-shadow: 0 0 15px rgba(0,217,255,0.8), 0 0 30px rgba(0,217,255,0.6);">
            &lt; Additional_Information /&gt;
          </h3>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-5 text-base sm:text-lg text-gray-300 font-mono">
            <div v-for="(info, index) in additionalInfo" :key="index"
                 class="flex items-start gap-3 group/item hover:translate-x-2 transition-transform"
                 :class="{ 'sm:col-span-2': index === additionalInfo.length - 1 }">
              <span class="text-cyber-green mt-1 group-hover/item:text-cyber-blue transition-colors font-bold text-lg"
                    style="text-shadow: 0 0 8px currentColor;">&gt;</span>
              <span class="group-hover/item:text-white transition-colors font-medium" v-html="info"></span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>