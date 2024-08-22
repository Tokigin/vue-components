<template>
  <div>
    <button @click="n++">+</button>
    <div>
      <input type="number" name="" id="" v-model="n" />
    </div>
    <button @click="n--">-</button>
    <button @click="n = 0">clear</button>
  </div>
</template>
<script setup>
import { ref } from "vue";
const n = ref(0);
</script>
<style scoped>
input {
  width: 50px;
}
div {
  padding: 5px;
  display: flex;
  justify-content: center;
}
</style>
