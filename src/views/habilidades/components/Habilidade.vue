<template>
  <div class="container">
    <slot></slot>
    <font-awesome-icon class="icon" :icon="icon" />
  </div>
</template>

<script setup>
defineProps({
  icon: {
    type: String,
    required: false,
  },
})

</script>

<style scoped>
.container{
  width: 160px;
  height: 160px;
  background-color: rgba(248, 248, 248, 0.712);
  border: 2px solid rgb(235, 235, 235);
  border-radius: 4px;
  box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.082);
  transition: ease 1s;
  display: flex;
  align-items: center;
  justify-content: center;
}
.container:hover{
  border: 2px solid var(--color-primary);
}

.icon{
  width: 90px;
  height: 90px;
  color: var(--color-secondary);
  transition: ease 1s;
}

</style>
