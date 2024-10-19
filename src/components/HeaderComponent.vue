<template>
  <header>
    <div class="conteiner-logo">
      <img
        src="../assets/images/logo-black.png"
        alt="logo geeek in code"
        class="logo"
      />
      <span class="name">Alice</span>
    </div>
    <nav class="router-links">
      <router-link to="#experiences" class="link">Experiências</router-link>
      <router-link to="#technologies" class="link">Tecnologias</router-link>
      <router-link to="#projects" class="link">Projetos</router-link>
      <router-link to="#contact" class="link">Contato</router-link>
    </nav>
  </header>
</template>

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
}

.link {
  text-decoration: none;
  color: black;
  font-family: 'MoreSugar';
  font-size: 20px;
  position: relative;
  overflow: hidden;
}

.link:hover {
  color: black;
  background: linear-gradient(270deg, #a211e6, #fb6ba2, #3ecfd4, #f04d5e);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: gradient-animation 5s ease infinite;
}
@media (max-width: 768px) {
  .name {
    display: none;
  }

  .router-links {
    display: none;
  }
}
</style>
