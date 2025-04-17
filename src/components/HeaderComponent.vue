<template>
  <header :class="[border]">
    <ul>
      <li>Início</li>
      <li>Sobre</li>
      <li>Habilidades</li>
      <li>Projetos</li>
      <li>Contato</li>
    </ul>
  </header>
</template>

<style scoped>
header {
  width: 100vw;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: end;
  position: fixed; 
  top: 0;
  left: 0;
  background-color: white;
  z-index: 1000; 
}

ul {
  display: flex;
  gap: 24px;
  list-style: none;
  padding-right: 24px;
}

li {
  font-size: 14px;
  font-weight: 400;
  cursor: pointer;
}
li:hover {
  color: var(--color-primary);
}

.border {
  border-bottom: 1px solid rgba(0, 0, 0, 0.315);
}

</style>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const border = ref('')

const handleScroll = () => {
  if (window.scrollY > 0) {
    border.value = 'border'
  } else {
    border.value = ''
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
