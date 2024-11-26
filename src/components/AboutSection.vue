<template>
  <div class="about">
    <video autoplay muted loop>
      <source src="../assets/videos/sky.mp4" type="video/mp4" />
    </video>
    <div class="content">
      <h1>Sobre Mim</h1>
      <p>Conteúdo sobre aqui.</p>
    </div>
  </div>
</template>

<style scoped>
.about {
  position: relative;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}

.about video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  object-fit: cover;
  opacity: 0.76;
}

.about .content {
  position: relative;
  z-index: 1;
  max-width: 1000px;
  margin: 0 auto;
  text-align: center;
}

.about .content h1 {
  margin: 0;
  padding: 0;
  font-size: 5.5em;
  text-transform: uppercase;
  color: #ffff;
}

.about .content p {
  font-size: 1.5em;
  color: #ffff;
}
</style>
