<script setup>
import Navbar from './components/Navbar.vue'
import HeroSection from './components/HeroSection.vue'
import BountyRewards from './components/BountyRewards.vue'
import RulesSection from './components/RulesSection.vue'
import FooterCTA from './components/FooterCTA.vue'
import AppFooter from './components/AppFooter.vue'

const scrollToSection = (sectionId) => {
  const element = document.getElementById(sectionId)
  if (element) {
    element.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<template>
  <div class="bg-black text-white font-mono overflow-x-hidden">
    <Navbar :scroll-to-section="scrollToSection" />
    <HeroSection :scroll-to-section="scrollToSection" />
    <BountyRewards />
    <RulesSection />
    <FooterCTA />
    <AppFooter />
  </div>
</template>