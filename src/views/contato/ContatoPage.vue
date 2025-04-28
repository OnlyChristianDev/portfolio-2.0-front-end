<template>
  <div class="main">
    <div class="contato">
      <h1>Fale comigo!</h1>
      <p>
        Ei! Ficou com alguma dúvida ou tem uma proposta? Me conte mais sobre sua ideia, vamos
        conversar!.
      </p>
      <form @submit.prevent="enviarEmail" method="post">
        <div class="email">
          <InputComponent v-model="nome" placeholder="Seu nome" />
          <InputComponent v-model="email" placeholder="Seu e-mail" />
        </div>
        <div class="container-textarea">
          <TextAreaComponent v-model="descricao" />
        </div>
        <button class="button-form">
          <span>Enviar <font-awesome-icon class="icon" :icon="faArrowRight" /></span>
        </button>
      </form>
      <div class="redes-sociais">
        <AboutMedias href="https://github.com/OnlyChristianDev" :icon="faGithub" />
        <AboutMedias href="https://www.linkedin.com/in/christiangdev" :icon="faLinkedin" />
        <AboutMedias @click="redirecionaGmail" :icon="faEnvelope" />
      </div>
    </div>
  </div>
</template>

<script setup>
import AboutMedias from '../sobre/components/AboutMedias.vue'
import TextAreaComponent from './components/TextAreaComponent.vue'
import InputComponent from './components/InputComponent.vue'
import { faGithub, faLinkedin } from '@fortawesome/free-brands-svg-icons'
import { faEnvelope, faArrowRight } from '@fortawesome/free-solid-svg-icons'
import { ref } from 'vue'

const nome = ref('')
const email = ref('')
const descricao = ref('')

const emailData = ref({
  nome: '',
  email: '',
  mensagem: ''
})

const enviaEmail = () => {

}

const redirecionaGmail = () => {
  window.open('https://mail.google.com/mail/?view=cm&to=christiandeveloper123@gmail.com', '_blank')
}
</script>

<style scoped src="../contato/contato.css"></style>
