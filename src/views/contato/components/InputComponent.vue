<template>
    <input  :placeholder="placeholder" type="text" />
</template>

<script setup>
defineProps({
  placeholder:{
    type: String,
    required: true,
  }
})
</script>

<style scoped>
input{
  font-weight: 300;
  outline: none;
  border: none;
  border-bottom: 1px solid gray;
  width: 50%;
  font-size: 15px;
  padding-bottom: 10px;
  color: gray;
}

input::placeholder{
  font-family: Poppins;
  font-weight: 300;
}

input:focus {
  border-bottom: 1px solid  var(--color-secondary);
  color: var(--color-secondary);
}
input:focus::placeholder{
  color: transparent;
}

</style>
