<template>
  <div class="main">
    <div class="contato">
      <h1>Fale comigo!</h1>
      <p>
        Ei! Ficou com alguma dúvida ou tem uma proposta? Me conte mais sobre sua ideia, vamos
        conversar!.
      </p>
      <div class="email">
        <InputComponent placeholder="Seu nome" />
        <InputComponent placeholder="Seu e-mail" />
      </div>
      <div class="container-textarea">
        <TextAreaComponent />
      </div>
      <div class="redes-sociais">
        <AboutMedias :icon="faGithub" />
        <AboutMedias :icon="faLinkedin" />
        <AboutMedias :icon="faEnvelope" />
      </div>
    </div>
  </div>
</template>

<script setup>
import AboutMedias from '../sobre/components/AboutMedias.vue'
import TextAreaComponent from './components/TextAreaComponent.vue'
import InputComponent from './components/InputComponent.vue'
import { faGithub, faLinkedin } from '@fortawesome/free-brands-svg-icons'
import { faEnvelope } from '@fortawesome/free-solid-svg-icons'
</script>

<style scoped src="../contato/contato.css"></style>
