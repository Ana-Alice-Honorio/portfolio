<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'HeaderComponent',
})
</script>

<template>
  <header>
    <nav>
      <router-link to="#experiences">Experiências</router-link>
      <router-link to="#technologies">Tecnologias</router-link>
      <router-link to="#projects">Projetos</router-link>
      <router-link to="#contact">Contato</router-link>
    </nav>
  </header>
</template>

<style scoped></style>
