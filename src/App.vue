<template>
  <HeaderComponent />
  <InicioPage />
  <SobrePage />
  <HabilidadesPage />
  <ProjetosPage />
  <ContatoPage />
</template>

<script setup>
import ContatoPage from './views/contato/ContatoPage.vue';
import ProjetosPage from './views/projetos/ProjetosPage.vue';
import HabilidadesPage from './views/habilidades/HabilidadesPage.vue';
import SobrePage from './views/sobre/SobrePage.vue';
import InicioPage from './views/inicio/InicioPage.vue';
import HeaderComponent from './components/HeaderComponent.vue';
</script>
