<template>
  <section id="home" class="home">
    <div class="home__container">
      <div class="home__headline">
        <div class="home__name">
          <h1>Denis</h1>
          <h2>Novik</h2>
        </div>

        <p class="home__subtitle">
          {{ t("home_subtitle") }}
        </p>

        <!-- language switcher -->
        <div class="home__language" aria-label="Select language">
          <button
            class="lang-btn"
            :class="{ 'lang-btn--active': lang.value === 'ru' }"
            @click="onClick('ru')"
            :aria-pressed="lang.value === 'ru'"
            :disabled="lang.value === 'ru'"
            type="button"
          >
            RU
          </button>

          <span class="lang-sep" aria-hidden="true">|</span>

          <button
            class="lang-btn"
            :class="{ 'lang-btn--active': lang.value === 'en' }"
            @click="onClick('en')"
            :aria-pressed="lang.value === 'en'"
            :disabled="lang.value === 'en'"
            type="button"
          >
            ENG
          </button>
        </div>
      </div>

      <div class="home__portrait">
        <img src="@/assets/portrait.png" alt="Denis Novik portrait" />
      </div>
    </div>
  </section>
</template>

<script setup>
import { inject } from "vue"

const t = inject("t")
const setLang = inject("setLang")
const lang = inject("lang")

const onClick = (clickedLang) => {
  if (!lang || !setLang) return
  if (clickedLang === lang.value) return
  setLang(clickedLang)
}
</script>
