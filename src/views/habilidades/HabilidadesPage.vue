<template>
  <div class="main">
    <h2>Habilidades</h2>
    <div class="grid-habiidades">
      <Habilidade :icon="faHtml5" />
      <Habilidade :icon="faCss3Alt" />
      <Habilidade :icon="faJs" />
      <Habilidade  />
      <Habilidade :icon="faVuejs" />
      <Habilidade :icon="faReact" />
      <Habilidade :icon="faNodeJs"/>
      <Habilidade :icon="faFigma"/>
      <Habilidade :icon="faGithub"/>
      <Habilidade :icon="faGitAlt"/>
      <Habilidade  />
      <Habilidade  />
    </div>
  </div>
</template>

<script setup>
import { faHtml5, faCss3Alt, faJs, faVuejs, faReact, faNodeJs, faFigma, faGithub, faGitAlt} from '@fortawesome/free-brands-svg-icons'
import Habilidade from './components/Habilidade.vue'
</script>

<style src="../habilidades/habilidades.css" scoped></style>
