<template>
  <div class="main">
    <div class="about-me">
      <div class="image">
        <Vue3Lottie width="500px" :animationData="aboutAnimation" :loop="true" />
      </div>
      <div class="description">
        <h4>Sobre mim.</h4>
        <h2>Christian Gabriel</h2>
        <h3>Desenvolvedor Frontend</h3>
        <p>
          Atualmente, atuo em múltiplos projetos como desenvolvedor Frontend, trabalhando no
          desenvolvimento, evolução e modernização de aplicações web. Tenho experiência com Angular,
          Vue, React e TypeScript, atuando com autonomia na implementação de funcionalidades,
          refatoração e melhoria de aplicações.
        </p>
        <div class="social-medias">
          <AboutMedias
            v-for="social in socialMedias"
            :key="social.name"
            :href="social.href"
            :icon="social.icon"
            @click="openLink(social.href)"
          />
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

const socialMedias = [
  {
    name: 'GitHub',
    href: 'https://github.com/christian-gab',
    icon: faGithub,
  },
  {
    name: 'LinkedIn',
    href: 'https://www.linkedin.com/in/christiangdev',
    icon: faLinkedin,
  },
  {
    name: 'Email',
    href: 'https://mail.google.com/mail/?view=cm&to=christiandeveloper123@gmail.com',
    icon: faEnvelope,
  },
]

const openLink = (href) => {
  window.open(href, '_blank')
}
</script>

<style src="/src/views/sobre/sobre.css" scoped></style>
