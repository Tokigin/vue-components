<template>
  <div
    ref="target"
    :style="{
      transform: Card,
      transition: 'transform 0.25s ease-out',
    }"
  ></div>
</template>
<script setup>
import { ref, computed } from "vue";
import { useMouseInElement } from "@vueuse/core";

const target = ref(null);
const { elementX, elementY, isOutside, elementHeight, elementWidth } =
  useMouseInElement(target);

const Card = computed(() => {
  const MAX_ROTATION = 16;
  const rX = (
    MAX_ROTATION / 2 -
    (elementY.value / elementHeight.value) * MAX_ROTATION
  ).toFixed(2);
  const rY = (
    (elementX.value / elementWidth.value) * MAX_ROTATION -
    MAX_ROTATION / 2
  ).toFixed(2);

  return isOutside.value
    ? ""
    : `perspective(${elementWidth.value}px)rotateX(${rX}deg) rotateY(${rY}deg)`;
});
</script>
<style scoped>
div {
  position: absolute;
  width: 30rem;
  height: 20rem;
  background-color: #1a1a1a;
  padding: 1rem;
  margin: 1rem;
  border-radius: 1rem;
}
</style>
