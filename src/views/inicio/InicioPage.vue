<template>
  <div class="main">
    <div class="description-me">
      <h1>Olá, eu sou o <span class="destaque">Christian.</span></h1>
      <p>
        Sou um
        <span ref="typeTarget" class="destaque"></span>
        apaixonado por criar interfaces web intuitivas e visualmente atraentes. Combinando
        habilidades em desenvolvimento web e design
        <span class="destaque">UI/UX.</span>
      </p>

      <div class="social-medias">
        <SociaMedia href="https://github.com/OnlyChristianDev" :icon="faGithub" />
        <SociaMedia href="https://www.linkedin.com/in/christiangdev" :icon="faLinkedin" />
        <SociaMedia @click="enviaEmail" :icon="faEnvelope" />
      </div>
      <a href="/public/curriculo.pdf" download="Curriculo Christian Front-End.pdf">
        <button class="download-cv">Download CV</button>
      </a>
    </div>

    <div class="animation">
      <Vue3Lottie width="500px" :animationData="animationData" :loop="true" />
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'
import TypeIt from 'typeit'
import SociaMedia from './components/SociaMedia.vue'
import { faGithub, faLinkedin } from '@fortawesome/free-brands-svg-icons'
import { faEnvelope } from '@fortawesome/free-solid-svg-icons'
import { Vue3Lottie } from 'vue3-lottie'
import animationData from '@/assets/animation/animation.json'

const typeTarget = ref(null)

onMounted(() => {
  new TypeIt(typeTarget.value, {
    speed: 100,
    loop: true,
    cursor: true,
  })
    .type('desenvolvedor frontend')
    .pause(5000)
    .delete()
    .type('entusiasta do design gráfico')
    .pause(5000)
    .delete()
    .go()
})

const enviaEmail = () => {
  window.open('https://mail.google.com/mail/?view=cm&to=christiandeveloper123@gmail.com', '_blank');
}

</script>

<style scoped src="@/views/inicio/Inicio.css"></style>
