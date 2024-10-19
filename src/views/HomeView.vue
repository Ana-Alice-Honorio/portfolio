<template>
  <div>
    <HeaderComponent />
    <AboutSection />
    <ExperiencesSection />
    <TechnologiesSection />
    <ProjectsSection />
    <ContactSection />

    <button v-if="showButton" @click="scrollToTop" class="scroll-to-top">
      Volte ao Topo
    </button>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue'
import HeaderComponent from '../components/HeaderComponent.vue'
import AboutSection from '../components/AboutSection.vue'
import ExperiencesSection from '../components/ExperiencesSection.vue'
import TechnologiesSection from '../components/TechnologiesSection.vue'
import ProjectsSection from '../components/ProjectsSection.vue'
import ContactSection from '../components/ContactSection.vue'

const showButton = ref(false)

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

const handleScroll = () => {
  showButton.value = window.scrollY > 200
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.scroll-to-top {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background-color: white;
  color: black;
  border: none;
  padding: 10px 15px;
  border-radius: 50%;
  cursor: pointer;
  font-size: 14px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
  transition: opacity 0.3s ease;
  font-family: 'MoreSugar';
}

.scroll-to-top:hover {
  color: black;
  background: #e2ffff;
}

.scroll-to-top:active {
  background-color: white;
}
</style>
