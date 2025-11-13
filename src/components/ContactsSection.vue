<template>
  <section id="contacts" class="contacts">
    <div class="contacts__container">
      <h3>Contacts</h3>
      <p class="contacts__description">
        Want to know more or just chat? You are welcome!
      </p>
      <button class="contacts__button">Send message</button>

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

      <p class="contacts__note">Like me on LinkedIn, Instagram, Behance, Dribbble</p>
    </div>
  </section>
</template>

<script setup>
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
