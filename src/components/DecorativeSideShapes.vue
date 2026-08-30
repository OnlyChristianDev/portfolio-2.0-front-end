<template>
  <div ref="decorativeRef" class="side-decoration" aria-hidden="true">
    <div class="effect-left">
      <Vue3Lottie :animationData="sideEffectData" :loop="true" :autoPlay="true" />
    </div>

    <div class="effect-right">
      <Vue3Lottie :animationData="sideEffectData" :loop="true" :autoPlay="true" />
    </div>
  </div>
</template>

<script setup>
import { onBeforeUnmount, onMounted, useTemplateRef } from 'vue'
import { Vue3Lottie } from 'vue3-lottie'
import sideEffectData from '@/assets/animation/SideEffect.json'

const decorativeRef = useTemplateRef('decorativeRef')

const updateDecoration = () => {
  if (!decorativeRef.value) return

  const scale = Math.min(1.3, 0.3 + (window.scrollY / 1000) * 1)

  const translateProgress = Math.min(1, window.scrollY / 600)
  const translateLeft = translateProgress * 350
  const translateRight = -translateProgress * 350

  const opacity = Math.min(1, Math.max(0, (window.scrollY - 100) / 300))
  const opacityOut = Math.max(0, 1 - Math.max(0, (window.scrollY - 2600) / 600))
  const finalOpacity = Math.min(opacity, opacityOut)

  decorativeRef.value.style.setProperty('--effect-left-translate', `${translateLeft}px`)
  decorativeRef.value.style.setProperty('--effect-right-translate', `${translateRight}px`)
  decorativeRef.value.style.setProperty('--effect-scale', scale.toFixed(3))
  decorativeRef.value.style.setProperty('--decoration-opacity', finalOpacity.toFixed(3))
}

onMounted(() => {
  updateDecoration()
  window.addEventListener('scroll', updateDecoration, { passive: true })
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', updateDecoration)
})
</script>

<style scoped>
.side-decoration {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  pointer-events: none;
  z-index: 0;
  opacity: var(--decoration-opacity, 0);
}

.effect-left {
  position: absolute;
  width: 400px;
  height: 400px;
  left: -600px;
  top: 15%;
  transform: translateX(var(--effect-left-translate, 0px)) scale(var(--effect-scale, 0.3));
  opacity: 0.2;
}

.effect-right {
  position: absolute;
  width: 400px;
  height: 400px;
  right: -600px;
  bottom: 15%;
  transform: translateX(var(--effect-right-translate, 0px)) scale(var(--effect-scale, 0.3));
  opacity: 0.2;
}
</style>
