<template>
  <textarea v-model="value" placeholder="Descreva sua ideia ou projeto aqui, com todos os detalhes necessários." name="" id=""></textarea>
</template>

<script setup>
const value = defineModel()
</script>
<style scoped>
textarea {
  font-weight: 300;
  outline: none;
  padding: 10px 0 0 0;
  border: none;
  border-bottom: 1px solid rgb(153, 153, 153);
  width: 100%;
  font-size: 15px;
  line-height: 1;
  color: rgb(153, 153, 153);
  resize: none;
  font-family: Poppins;
  transition: 0.2s ease-in-out;
  font-size: 16px;

}

textarea::placeholder {
  font-family: Poppins;
  color: rgb(153, 153, 153);
  opacity: 1;
  font-size: 16px;
  transition: opacity 0.2s ease;
}

textarea:focus::placeholder{
  opacity: 0;
}

textarea:focus {
  border-color: var(--color-primary);
  color: var(--color-primary);
}


</style>
