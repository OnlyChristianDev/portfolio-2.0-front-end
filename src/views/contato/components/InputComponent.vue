<template>
    <input v-model="value" :placeholder="placeholder" type="text" />
</template>

<script setup>
defineProps({
  placeholder:{
    type: String,
    required: true,
  }
})

const value = defineModel()
</script>

<style scoped>
input{
  font-weight: 300;
  outline: none;
  border: none;
  border-bottom: 1px solid rgb(153, 153, 153);
  width: 50%;
  font-size: 15px;
  padding-bottom: 10px;
  color: rgb(153, 153, 153);
  font-family: Poppins;
  transition: 0.2s ease-in-out;
  font-size: 16px;
}

input::placeholder{
  font-family: Poppins;
  font-weight: 300;
  font-size: 16px;
  transition: opacity 0.2s ease;
  opacity: 1;
}

input:focus {
  border-bottom: 1px solid  var(--color-secondary);
  color: var(--color-secondary);
}

input:focus::placeholder{
  opacity: 0;
}

</style>
