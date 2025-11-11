<script setup>
const props = defineProps({
  place: String,
  amount: String,
  color: String,
  rank: Number
})

const colorClasses = {
  red: {
    glow: 'from-cyber-red to-red-900',
    border: 'border-cyber-red',
    text: 'text-cyber-red',
    shadow: 'drop-shadow-[0_0_20px_rgba(255,0,0,0.8)]'
  },
  silver: {
    glow: 'from-gray-400 to-gray-600',
    border: 'border-gray-400',
    text: 'text-gray-300',
    shadow: 'drop-shadow-[0_0_20px_rgba(156,163,175,0.6)]'
  },
  bronze: {
    glow: 'from-gray-500 to-gray-700',
    border: 'border-gray-500',
    text: 'text-gray-400',
    shadow: 'drop-shadow-[0_0_20px_rgba(107,114,128,0.5)]'
  }
}

const classes = colorClasses[props.color]
</script>

<template>
  <div class="relative group" :class="{ 'sm:col-span-2 md:col-span-1': rank === 3 }">
    <div class="absolute inset-0 blur-xl opacity-50 group-hover:opacity-75 transition-opacity bg-gradient-to-br"
         :class="classes.glow"></div>
    <div class="relative bg-black border-2 p-8 text-center transform hover:-translate-y-2 transition-all"
         :class="classes.border">
      <div class="mb-6">
        <!-- Trophy icon for 1st place, medals for others -->
        <svg v-if="rank === 1" class="w-20 h-20 mx-auto" :class="[classes.text, classes.shadow]" fill="currentColor" viewBox="0 0 24 24">
          <path d="M20 2H4v2h2.62l-2.5 12H5v5h14v-5h.88l-2.5-12H20V2zm-7 15c-1.65 0-3-1.35-3-3s1.35-3 3-3 3 1.35 3 3-1.35 3-3 3zm1.5-9l-1.5 2-1.5-2h3z"/>
        </svg>
        <svg v-else class="w-20 h-20 mx-auto" :class="[classes.text, classes.shadow]" fill="currentColor" viewBox="0 0 24 24">
          <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"/>
          <circle cx="12" cy="12" r="4"/>
        </svg>
      </div>
      <div class="text-sm uppercase tracking-widest mb-2" :class="color === 'bronze' ? 'text-gray-500' : 'text-gray-400'">
        {{ place }} Place
      </div>
      <div class="text-5xl font-bold mb-2" :class="[classes.text, classes.shadow]">
        {{ amount }}
      </div>
      <div class="text-base uppercase tracking-wider" :class="color === 'bronze' ? 'text-gray-500' : 'text-gray-400'">
        BDT
      </div>
    </div>
  </div>
</template>
