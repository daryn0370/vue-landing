<script setup>
import { ref, provide } from 'vue'

const saved = localStorage.getItem('site_lang')
const lang = ref(saved === 'ru' ? 'ru' : 'en')

const dictionary = {
  en: {
    home_subtitle: "UX | UI designer, 24 years old, Minsk",
    about_h3: "About me",
    about_p1: "Hi, I'm Denis - UX/UI designer from Minsk. I'm interested in design and everything connected with it.",
    about_p2: "I'm studying at courses \"Web and mobile design interfaces\" in IT-Academy.",
    about_p3: "Ready to implement excellent projects with wonderful people.",
    contacts_h3: "Contacts",
    contacts_desc: "Want to know more or just chat? You are welcome!",
    contacts_btn: "Send message",
    contacts_note: "Like me on LinkedIn, Instagram, Behance, Dribbble",
    skills_h3: "Skills",
    skills_subtitle: "I work in such programs as",
    portfolio_h3: "Portfolio",
    nav_home: "Home",
    nav_about: "About me",
    nav_skills: "Skills",
    nav_portfolio: "Portfolio",
    nav_contacts: "Contacts",
  },
  ru: {
    home_subtitle: "UX | UI дизайнер, 24 года, Минск",
    about_h3: "Обо мне",
    about_p1: "Привет, я Денис — UX/UI дизайнер из Минска. Интересуюсь дизайном и всем, что с ним связано.",
    about_p2: "Учусь на курсе «Web и мобильные интерфейсы» в IT-Academy.",
    about_p3: "Готов создавать отличные проекты с замечательными людьми.",
    contacts_h3: "Контакты",
    contacts_desc: "Хочешь узнать больше или просто пообщаться? Добро пожаловать!",
    contacts_btn: "Отправить сообщение",
    contacts_note: "Поддержи меня в LinkedIn, Instagram, Behance, Dribbble",
    skills_h3: "Навыки",
    skills_subtitle: "Я работаю в таких программах как",
    portfolio_h3: "Портфолио",
    nav_home: "Главная",
    nav_about: "Обо мне",
    nav_skills: "Навыки",
    nav_portfolio: "Портфолио",
    nav_contacts: "Контакты",
  }
}

const t = (key) => {
  const group = dictionary[lang.value] || dictionary.en
  return group[key] ?? key
}

const setLang = (value) => {
  if (value !== 'en' && value !== 'ru') return
  if (lang.value === value) return
  lang.value = value
  try { localStorage.setItem('site_lang', value) } catch(e) {}
}

const switchLang = () => {
  setLang(lang.value === 'en' ? 'ru' : 'en')
}

provide('t', t)
provide('setLang', setLang)
provide('switchLang', switchLang)
provide('lang', lang)
</script>

<template>
  <slot />
</template>
