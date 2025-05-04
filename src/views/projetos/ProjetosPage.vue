<template>
  <div class="main">
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

const projetoAtual = ref(0)
const projects = [
  { title: 'Título 1', description: '', image: '/img/1.jpg' },
  { title: 'Título 2', description: 'Lorem ipsum…', image: '/img/2.jpg' },
]

const currentProject = computed(() => projects[projetoAtual.value])

const nextSlide = () => {
  projetoAtual.value = (projetoAtual.value + 1) % projects.length
}

const prevSlide = () => {
  projetoAtual.value =
    (projetoAtual.value - 1 + projects.length) % projects.length
}

setInterval(() => {
nextSlide()
}, 5000);
</script>

<style scoped src="../projetos/projetos.css"></style>
