<template>
  <div class="cursor" :style="{ left: `${x}px`, top: `${y}px` }"></div>
</template>
<script setup>
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
  pointer-events: none;
}
</style>
