<template>
  <div class="main">
    <div class="description-me">
      <h1>Olá, eu sou o <span class="destaque">Christian.</span></h1>
      <p>Sou um <span class="destaque">desenvolvedor frontend</span> apaixonado por criar interfaces web intuitivas e visualmente atraentes. Combinando habilidades em desenvolvimento web e design <span class="destaque">UI/UX.</span></p>
      <div class="social-medias">
        <SociaMedia :icon="faGithub" />
        <SociaMedia :icon="faLinkedin" />
        <SociaMedia :icon="faEnvelope" />
      </div>
      <button class="download-cv">Download CV</button>
    </div>
    <div>
      <Vue3Lottie :animationData="animationData" :loop="true" />
    </div>
  </div>
</template>

<script setup>
import SociaMedia from './components/SociaMedia.vue';
import { faGithub, faLinkedin } from '@fortawesome/free-brands-svg-icons';
import { faEnvelope } from '@fortawesome/free-solid-svg-icons';
import { Vue3Lottie } from 'vue3-lottie';
import animationData from "@/assets/animation/animation.json"
</script>

<style scoped src="@/views/inicio/Inicio.css">

</style>
