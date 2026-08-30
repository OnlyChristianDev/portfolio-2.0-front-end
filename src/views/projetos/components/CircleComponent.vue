<template>
  <div class="circle" :class="{ active }"></div>
</template>

<script setup>
  defineProps({
    active: {
      type: Boolean,
      default: false
    }
  })
</script>

<style scoped>
.circle {
  width: 8px;
  height: 8px;
  background-color: rgb(170, 169, 169);
  border-radius: 50%;
  cursor: pointer;
}

.circle:hover {
  background-color: var(--color-tertiary)
}

.active {
  background-color: var(--color-primary);
}
</style>
