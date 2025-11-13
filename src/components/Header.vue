<template>
  <header class="header">
    <div class="container">
      <button
        class="nav-toggle"
        :aria-expanded="isMenuOpen"
        aria-label="Toggle navigation"
        @click="toggleMenu"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>

      <nav class="nav" :class="{ 'nav--open': isMenuOpen }">
        <ul>
          <li v-for="item in navItems" :key="item.id">
            <a
              :href="item.link"
              :class="{ active: activeSection === item.id }"
              @click="handleNavClick(item.id)"
            >
              {{ item.label }}
            </a>
          </li>
        </ul>
      </nav>
    </div>

    <div
      class="nav-overlay"
      v-if="isMenuOpen"
      @click="closeMenu"
    ></div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted, watch } from 'vue'

const navItems = [
  { id: 'home', label: 'Home', link: '#home' },
  { id: 'about', label: 'About me', link: '#about' },
  { id: 'skills', label: 'Skills', link: '#skills' },
  { id: 'portfolio', label: 'Portfolio', link: '#portfolio' },
  { id: 'contacts', label: 'Contacts', link: '#contacts' },
]

const activeSection = ref('home')
const isMenuOpen = ref(false)

const setActive = (id) => {
  activeSection.value = id
}

const closeMenu = () => {
  isMenuOpen.value = false
}

const handleNavClick = (id) => {
  setActive(id)
  closeMenu()
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const handleResize = () => {
  if (window.innerWidth >= 769) {
    closeMenu()
  }
}

watch(isMenuOpen, (isOpen) => {
  document.body.style.overflow = isOpen ? 'hidden' : ''
})

onMounted(() => {
  const hash = window.location.hash.replace('#', '')
  if (hash) activeSection.value = hash
  window.addEventListener('resize', handleResize)
})

onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
  document.body.style.overflow = ''
})
</script>
