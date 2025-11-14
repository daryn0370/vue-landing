<template>
  <section id="contacts" class="contacts">
    <div class="contacts__container">
      <h3>{{ t("contacts_h3") }}</h3>

      <p class="contacts__description">
        {{ t("contacts_desc") }}
      </p>

      <button class="contacts__button">
        {{ t("contacts_btn") }}
      </button>

      <div class="contacts__socials">
        <a
          v-for="item in socials"
          :key="item.label"
          :href="item.href"
          :aria-label="item.label"
          target="_blank"
          rel="noopener"
        >
          <img :src="item.icon" :alt="item.label" />
        </a>
      </div>

      <p class="contacts__note">{{ t("contacts_note") }}</p>
    </div>
  </section>
</template>

<script setup>
import { inject } from "vue"
const t = inject("t")

const socials = [
  {
    label: 'LinkedIn',
    icon: new URL('../assets/linkedin.png', import.meta.url).href,
    href: '#',
  },
  {
    label: 'Instagram',
    icon: new URL('../assets/instagram.png', import.meta.url).href,
    href: '#',
  },
  {
    label: 'Behance',
    icon: new URL('../assets/Be.png', import.meta.url).href,
    href: '#',
  },
  {
    label: 'Dribbble',
    icon: new URL('../assets/ball.png', import.meta.url).href,
    href: '#',
  },
]
</script>
