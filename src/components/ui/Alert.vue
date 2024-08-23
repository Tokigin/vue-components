<template>
  <div v-if="open">
    <h3>Alert Message</h3>
    <button @click="open = !open">X</button>
  </div>

  <button @click="open = !open">open alert</button>
</template>
<script setup>
import { ref } from "vue";
const open = ref(true);
</script>
<style scoped>
div {
  width: 60rem;
  background-color: #242424;
  border: solid 0.1rem;
  border-radius: 1rem;
  display: flex;
  justify-content: space-between;
  padding-left: 1rem;
  padding-left: 1rem;
}
</style>
