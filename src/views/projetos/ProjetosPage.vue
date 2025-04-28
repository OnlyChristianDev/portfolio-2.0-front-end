<template>
  <div class="main">
    <h1 class="title">Projetos</h1>
    <div class="projetos-main">
      <font-awesome-icon class="icon" :icon="faChevronLeft" />
      <div class="container-projetos">
        <div class="projetos">
          <div class="image-project"></div>
          <div class="descricao-projeto">
            <h1>Titulo</h1>
            <p>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Hic architecto totam
              corrupti, laboriosam consectetur explicabo pariatur laudantium fugiat veritatis
              eveniet quis ab, expedita quibusdam maxime quo itaque maiores? Tenetur, obcaecati.
            </p>
            <button>
              Confira
              <font-awesome-icon class="icon-arrow" :icon="faArrowRight" />
            </button>
          </div>
        </div>
        <div class="circles-components">
          <CircleComponent v-for="(project, index) in projects" :key="index" />
        </div>
      </div>
      <font-awesome-icon class="icon" :icon="faChevronRight" />
    </div>
  </div>
</template>

<script setup>
const projects = [1, 2, 4, 5, 6, 7]
import { faArrowRight } from '@fortawesome/free-solid-svg-icons'
import CircleComponent from './components/CircleComponent.vue'
import { faChevronLeft, faChevronRight } from '@fortawesome/free-solid-svg-icons'
</script>

<style scoped src="../projetos/projetos.css"></style>
