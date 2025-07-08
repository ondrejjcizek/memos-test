<script setup lang="ts">
import '@/assets/main.css'
import MainNavigation from './components/MainNavigation.vue'
import HeroSection from '@/views/HeroSection.vue'
import FeaturesSection from '@/views/FeaturesSection.vue'
import CallToAction from '@/views/CallToAction.vue'
import ContactSection from './views/ContactSection.vue'
import PricingTable from './views/PricingTable.vue'
import MainFooter from './views/MainFooter.vue'
</script>

<template>
  <MainNavigation />
  <HeroSection />
  <FeaturesSection />
  <CallToAction />
  <ContactSection />
  <PricingTable />
  <MainFooter />
</template>
