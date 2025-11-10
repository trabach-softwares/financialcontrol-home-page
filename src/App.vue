<template>
  <div class="app">
    <Header />
    <main>
      <HeroSection />
      <DashboardPreview />
      <FeaturesSection />
      <AnalyticsSection />
      <SecuritySection />
      <PricingSection />
    </main>
    <Footer />
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import HeroSection from './components/HeroSection.vue'
import DashboardPreview from './components/DashboardPreview.vue'
import FeaturesSection from './components/FeaturesSection.vue'
import AnalyticsSection from './components/AnalyticsSection.vue'
import SecuritySection from './components/SecuritySection.vue'
import PricingSection from './components/PricingSection.vue'
import Footer from './components/Footer.vue'
</script>

<style scoped>
.app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

main {
  flex: 1;
}
</style>
