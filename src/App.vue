<template>
  <Translation>
    <div id="app">
      <Header />

      <div 
        class="header-divider" 
        aria-hidden="true"
      ></div>

      <main>
        <HomeSection />
        <AboutMeSection />
        <SkillsSection />
        <PortfolioSection />
        <ContactsSection />
      </main>
    </div>
  </Translation>
</template>

<script setup>
import Translation from '@/components/Translation.vue'

import Header from './components/Header.vue'
import HomeSection from './components/HomeSection.vue'
import AboutMeSection from './components/AboutMeSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import PortfolioSection from './components/PortfolioSection.vue'
import ContactsSection from './components/ContactsSection.vue'
</script>

<style>
/* если у тебя были стили — оставляй их тут */
</style>
