<template>
  <HeaderComponent />
  <InicioPage />
  <SobrePage />
  <HabilidadesPage />
  <ProjetosPage />
</template>

<script setup>
import ProjetosPage from './views/projetos/ProjetosPage.vue';
import HabilidadesPage from './views/habilidades/HabilidadesPage.vue';
import SobrePage from './views/sobre/SobrePage.vue';
import InicioPage from './views/inicio/InicioPage.vue';
import HeaderComponent from './components/HeaderComponent.vue';
</script>
