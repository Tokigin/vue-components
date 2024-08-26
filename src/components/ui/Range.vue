<template>
  <div>
    <div class="wrapper">
      <input type="range" min="0" max="100" v-model="n1" />
      <p>{{ n1 }}</p>
    </div>

    <div class="wrapper">
      <input type="range" min="0" max="100" step="10" v-model="n2" />
      <p>{{ n2 }}</p>
    </div>
  </div>
</template>
<script setup>
import { ref } from "vue";
const n1 = ref(30);
const n2 = ref(30);
</script>
<style scoped>
.wrapper {
  display: flex;
  gap: 1rem;
  align-items: center;
}
.wrapper::before,
.wrapper::after {
  display: block;
  position: absolute;
  z-index: 99;
  color: #fff;
  width: 100%;
  text-align: center;
  font-size: 1.5rem;
  line-height: 1;
  padding: 0.75rem 0;
  pointer-events: none;
}

input[type="range"] {
  appearance: none;
  background-color: rgba(255, 255, 255, 0.2);
  margin: 0;
  padding: 0;
  width: 20rem;
  height: 2.5rem;
  border-radius: 1rem;
  overflow: hidden;
}
input[type="range"][step] {
  background-color: transparent;
  background-image: repeating-linear-gradient(
    to right,
    rgba(255, 255, 255, 0.2),
    rgba(255, 255, 255, 0.2) calc(10% - 1px),
    #05051a 10%
  );
}
input[type="range"]::-webkit-slider-thumb {
  appearance: none;
  width: 0;
  box-shadow: -20rem 0 0 20rem rgba(255, 255, 255, 0.2);
}
input[type="range"]::-moz-range-thumb {
  border: none;
  width: 0;
  box-shadow: -20rem 0 0 20rem rgba(255, 255, 255, 0.2);
}
</style>
