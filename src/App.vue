<template>
  <div id="app">
    <Header />
    <img
      src="@/assets/Vector.png"
      alt=""
      class="header-divider"
      aria-hidden="true"
    />

    <main>
      <HomeSection />
      <AboutMeSection />
      <SkillsSection />
      <PortfolioSection />
      <ContactsSection />
    </main>
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import HomeSection from './components/HomeSection.vue'
import AboutMeSection from './components/AboutMeSection.vue'
import SkillsSection from './components/SkillsSection.vue'
import PortfolioSection from './components/PortfolioSection.vue'
import ContactsSection from './components/ContactsSection.vue'
</script>
