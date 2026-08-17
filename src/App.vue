<script setup>
import { onMounted } from 'vue'
import NavBar from './components/NavBar.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Experience from './components/Experience.vue'
import Education from './components/Education.vue'
import Skills from './components/Skills.vue'
import Contact from './components/Contact.vue'
import AppFooter from './components/AppFooter.vue'

onMounted(() => {
  const obs = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('in')
          obs.unobserve(entry.target)
        }
      })
    },
    { threshold: 0.15 }
  )
  document.querySelectorAll('.fade-up').forEach((el) => obs.observe(el))
})
</script>

<template>
  <div class="bg-grid"></div>
  <NavBar />
  <div class="wrap">
    <Hero />
    <About />
    <Experience />
    <Education />
    <Skills />
    <Contact />
    <AppFooter />
  </div>
</template>
