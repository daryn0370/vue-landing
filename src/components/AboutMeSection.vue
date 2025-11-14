<template>
  <section id="about" class="about">
    <div class="about__container">
      <h3>{{ t("about_h3") }}</h3>
      <p>{{ t("about_p1") }}</p>
      <p>{{ t("about_p2") }}</p>
      <p>{{ t("about_p3") }}</p>
    </div>
  </section>
</template>

<script setup>
import { inject } from "vue"
const t = inject("t")
</script>
