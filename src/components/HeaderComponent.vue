<template>
  <header :class="[border]">
    <ul>
      <li v-for="item in menuItems" :key="item.id" @click="scrollToSection(item.id)">
        {{ item.label }}
      </li>
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
  border-bottom: 1px solid transparent;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
  z-index: 1000;
}

ul {
  display: flex;
  gap: 24px;
  list-style: none;
  margin-right: 48px;
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
  border-color: rgba(0, 0, 0, 0.315);
  box-shadow: 0 1px 0 rgba(0, 0, 0, 0.10);
}
</style>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const border = ref('')

const menuItems = [
  { label: 'Início', id: 'inicio' },
  { label: 'Sobre', id: 'sobre' },
  { label: 'Habilidades', id: 'habilidades' },
  { label: 'Projetos', id: 'projetos' },
  { label: 'Contato', id: 'contato' },
]

const handleScroll = () => {
  if (window.scrollY > 0) {
    border.value = 'border'
  } else {
    border.value = ''
  }
}

const scrollToSection = (id) => {
  const section = document.getElementById(id)

  if (section) {
    section.scrollIntoView({ behavior: 'smooth', block: 'start' })
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
