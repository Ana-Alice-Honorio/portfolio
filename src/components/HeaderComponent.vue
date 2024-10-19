<template>
  <header class="white-bg">
    <div class="conteiner-logo">
      <img
        src="../assets/images/logo-black.png"
        alt="logo geeek in code"
        class="logo"
      />
      <span class="name">Alice</span>
    </div>
    <div class="menu-icon" @click="toggleMenu">
      <div class="bar" v-bind:class="{ active: isMenuOpen }"></div>
      <div class="bar" v-bind:class="{ active: isMenuOpen }"></div>
      <div class="bar" v-bind:class="{ active: isMenuOpen }"></div>
    </div>
    <nav class="router-links" v-bind:class="{ active: isMenuOpen }">
      <router-link to="#experiences" class="link" @click="toggleMenu"
        >Experiências</router-link
      >
      <router-link to="#technologies" class="link" @click="toggleMenu"
        >Tecnologias</router-link
      >
      <router-link to="#projects" class="link" @click="toggleMenu"
        >Projetos</router-link
      >
      <router-link to="#contact" class="link" @click="toggleMenu"
        >Contato</router-link
      >
    </nav>
  </header>
</template>

<script lang="ts">
export default {
  data() {
    return {
      isMenuOpen: false,
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    },
  },
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;
  padding: 20px;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  margin: 25px;
  border-style: groove;
}

.conteiner-logo {
  display: flex;
  align-items: center;
}

.logo {
  height: 82px;
  width: auto;
  margin-right: -15px;
}

.name {
  font-size: 28px;
  font-family: 'MoreSugar';
  background: linear-gradient(270deg, #a211e6, #fb6ba2, #3ecfd4, #f04d5e);
  background-size: 400%;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: gradient-animation 5s ease infinite;
}

@keyframes gradient-animation {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.router-links {
  display: flex;
  justify-content: space-around;
  flex-direction: row;
  gap: 5px;
  transition: max-height 0.3s ease;
  overflow: hidden;
}

.link {
  text-decoration: none;
  color: black;
  font-family: 'MoreSugar';
  font-size: 20px;
  position: relative;
  overflow: hidden;
  margin-left: 5px;
}

.link:hover {
  color: black;
  background: linear-gradient(270deg, #a211e6, #fb6ba2, #3ecfd4, #f04d5e);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: gradient-animation 5s ease infinite;
}

.menu-icon {
  display: none;
  flex-direction: column;
  cursor: pointer;
}

.bar {
  height: 3px;
  width: 30px;
  background-color: black;
  margin: 3px 0;
  transition: all 0.3s ease;
}

.active {
  background-color: transparent;
}

.active .bar:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.active .bar:nth-child(2) {
  opacity: 0;
}

.active .bar:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

@media (max-width: 768px) {
  .name {
    display: none;
  }

  .router-links {
    display: flex;
    flex-direction: column;
    position: absolute;
    top: 80px;
    left: 0;
    right: 0;
    background-color: white;
    border: 1px solid #ccc;
    z-index: 100;
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.3s ease;
  }

  .router-links.active {
    max-height: 300px;
  }

  .menu-icon {
    display: flex;
  }
}
</style>
