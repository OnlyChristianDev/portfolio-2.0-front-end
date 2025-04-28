<template>
  <div class="main">
    <div class="about-me">
      <div class="image">
        <Vue3Lottie width="500px" :animationData="aboutAnimation" :loop="true" />
      </div>
      <div class="description">
        <h4>Sobre mim.</h4>
        <h2>Christian Gabriel</h2>
        <h3>Frontend Developer & UX Designer</h3>
        <p>
          Atualmente, atuo na área, numa ageência de social media desenvolvendo interfaces modernas
          e eficientes com Vue, TypeScript, JavaScript e Tailwind CSS. Tenho experiência prática em
          projetos reais, focando em performance, acessibilidade e boas práticas de desenvolvimento.
        </p>
        <div class="social-medias">
          <AboutMedias href="https://github.com/OnlyChristianDev" :icon="faGithub" />
          <AboutMedias href="https://www.linkedin.com/in/christiangdev" :icon="faLinkedin" />
          <AboutMedias @click="enviaEmail" :icon="faEnvelope" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import aboutAnimation from '@/assets/animation/aboutAnimation.json'
import { Vue3Lottie } from 'vue3-lottie'
import AboutMedias from './components/AboutMedias.vue'
import { faGithub, faLinkedin } from '@fortawesome/free-brands-svg-icons'
import { faEnvelope } from '@fortawesome/free-solid-svg-icons'

const enviaEmail = () => {
  window.open('https://mail.google.com/mail/?view=cm&to=christiandeveloper123@gmail.com', '_blank');
}
</script>

<style src="/src/views/sobre/sobre.css" scoped></style>
