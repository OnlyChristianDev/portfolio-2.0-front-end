<template>
  <div class="container-social-media">
    <font-awesome-icon class="icon" :icon="icon" />
  </div>
</template>

<script setup>
defineProps({
  icon: {
    type: String,
    required: true,
  },
})

</script>

<style scoped>
.container-social-media {
  border-radius: 4px;
  border: 1px solid var(--color-primary);
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  cursor: pointer;
  margin-bottom: 10px;
}

.icon {
  color: var(--color-primary);
  width: 25px;
  height: 25px;
}
</style>
