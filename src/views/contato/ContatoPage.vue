<template>
<div class="main">
  <div class="contato">
    <h1>Fale comigo!</h1>
    <p>Tem alguma dúvida ou proposta? Vamos conversar.</p>
    <div class="email">
      <InputComponent placeholder="Seu nome" />
      <InputComponent placeholder="Seu e-mail"/>
    </div>
    <div>
      <TextAreaComponent />
    </div>
  </div>
</div>
</template>

<script setup>
import TextAreaComponent from './components/TextAreaComponent.vue';
import InputComponent from './components/InputComponent.vue';
</script>

<style scoped src="../contato/contato.css"></style>
