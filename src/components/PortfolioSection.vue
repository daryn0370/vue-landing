<template>
  <section id="portfolio" class="portfolio">
    <div class="portfolio__container">
      <h3>Portfolio</h3>

      <div class="portfolio__list">
        <article
          v-for="project in projects"
          :key="project.title"
          class="portfolio-card"
        >
          <img
            :src="project.image"
            :alt="project.title"
            class="portfolio-card__image"
            loading="lazy"
          />
          <p class="portfolio-card__title">
            {{ project.title }}
          </p>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: 'Online fashion store - Homepage',
    image: new URL('../assets/fashion_shop.png', import.meta.url).href,
  },
  {
    title: 'Reebok Store - Concept',
    image: new URL('../assets/reebok_store.png', import.meta.url).href,
  },
  {
    title: 'Braun Landing Page - Concept',
    image: new URL('../assets/braun_store.png', import.meta.url).href,
  },
]
</script>
