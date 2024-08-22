<template>
  <div class="cursor" :style="{ left: `${x}px`, top: `${y}px` }"></div>
  <div>{{ x }}</div>
  <div>{{ y }}</div>
</template>
<script setup>
import { ref } from "vue";
import { useMouse } from "@vueuse/core";
const { x, y } = useMouse();
</script>
<style scoped>
.cursor {
  z-index: 100;
  position: absolute;
  transform: translate(-50%, -50%);
  width: 50px;
  height: 50px;
  border-style: solid;
  border-radius: 10px;
  /* background-color: white; */
  pointer-events: none;
}
</style>
