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
    <div @click="prevSlide">
      <font-awesome-icon class="icon" :icon="faChevronLeft" />
    </div>
    <div class="container-projetos">
      <Transition name="slide" mode="out-in">
        <div class="projetos" :key="projetoAtual">
          <div class="image-project">
            <img />
          </div>
          <div class="descricao-projeto">
            <h1>{{ currentProject.title }}</h1>
            <p>{{ currentProject.description }}</p>
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
      </Transition>
      <div class="circles-components">
        <CircleComponent
          v-for="(project, index) in projects"
          :key="index"
          :active="index === projetoAtual"
          @click.native="projetoAtual = index"
        />
      </div>
    </div>

    <div @click="nextSlide">
      <font-awesome-icon class="icon" :icon="faChevronRight" />
    </div>
  </div>
</template>

<script setup>
import { faArrowRight } from '@fortawesome/free-solid-svg-icons'
import CircleComponent from './components/CircleComponent.vue'
import { faChevronLeft, faChevronRight } from '@fortawesome/free-solid-svg-icons'
import { computed, ref } from 'vue'
import projetos from './arrayProjetos'

const projetoAtual = ref(0)

const currentProject = computed(() => projetos[projetoAtual.value])

const nextSlide = () => {
  projetoAtual.value = (projetoAtual.value + 1) % projetos.length
}

const prevSlide = () => {
  projetoAtual.value = (projetoAtual.value - 1 + projetos.length) % projetos.length
}

setInterval(() => {
  nextSlide()
}, 7000)

</script>

<style scoped src="../projetos/projetos.css"></style>
