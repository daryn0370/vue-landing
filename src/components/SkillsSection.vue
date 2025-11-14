<template>
  <section id="skills" class="skills">
    <div class="skills__container">
      <h3>{{ t("skills_h3") }}</h3>
      <p class="skills__subtitle">{{ t("skills_subtitle") }}</p>

      <div class="skills__grid">
        <article
          v-for="skill in skills"
          :key="skill.title"
          class="skill-card"
        >
          <img :src="skill.icon" :alt="skill.title" class="skill-card__icon" />
          <h4>{{ skill.title }}</h4>

          <div class="skill-card__rating" role="img">
            <svg
              v-for="n in 5"
              :key="n"
              class="skill-card__star"
              viewBox="0 0 24 24"
              :data-filled="n <= skill.rating"
            >
              <path
                d="M12 2.4l2.7 6.1 6.6.5-5 4.3 1.5 6.4-5.8-3.6-5.8 3.6 1.5-6.4-5-4.3 6.6-.5z"
              />
            </svg>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
import { inject } from "vue"
const t = inject("t")

const skills = [
  {
    title: 'Adobe Photoshop',
    rating: 4,
    icon: new URL('../assets/Ps.png', import.meta.url).href,
  },
  {
    title: 'Adobe Illustrator',
    rating: 3,
    icon: new URL('../assets/Ai.png', import.meta.url).href,
  },
  {
    title: 'Adobe After Effects',
    rating: 4,
    icon: new URL('../assets/Ae.png', import.meta.url).href,
  },
  {
    title: 'Figma',
    rating: 4,
    icon: new URL('../assets/figma.png', import.meta.url).href,
  },
]
</script>
