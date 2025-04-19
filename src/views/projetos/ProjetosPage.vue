<template>
  <div class="main">
    <font-awesome-icon class="icon" :icon="faChevronLeft" />
    <div class="container-projetos">
      <div class="projetos"></div>
      <div class="circles-components">
        <CircleComponent v-for="(project, index) in projects" :key="index" />
      </div>
    </div>
    <font-awesome-icon class="icon" :icon="faChevronRight" />
  </div>
</template>

<script setup>
const projects = [1,2,4,5,6,7]
import CircleComponent from './components/CircleComponent.vue'
import { faChevronLeft, faChevronRight } from '@fortawesome/free-solid-svg-icons'
</script>

<style scoped src="../projetos/projetos.css"></style>
