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
          Atualmente, atuo na área, numa agência de social media desenvolvendo interfaces modernas
          e eficientes com Vue, React, TypeScript, JavaScript e Tailwind CSS. Tenho experiência prática em
          projetos reais, focando em performance, acessibilidade e boas práticas de desenvolvimento.
        </p>
        <div class="social-medias">
          <AboutMedias :icon="faGithub" />
          <AboutMedias :icon="faLinkedin" />
          <AboutMedias :icon="faEnvelope" />
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
</script>

<style src="/src/views/sobre/sobre.css" scoped></style>
