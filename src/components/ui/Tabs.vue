<script setup>
import { ref, h, onMounted } from "vue";
import C1 from "../sections/C1.vue";
import C2 from "../sections/C2.vue";
import C3 from "../sections/C3.vue";

const data = ref(h(C1));
const dataC = (d) => {
  switch (d) {
    case "1":
      data.value = h(C1);
      break;
    case "2":
      data.value = h(C2);
      break;
    case "3":
      data.value = h(C3);
      break;
  }
};

const change = ref(false);
</script>
<template>
  <div>
    <button @click="change = !change">change direction</button>
  </div>
  <div :class="change ? 'switch' : ''">
    <div :class="change ? 'switch-btn' : ''">
      <button @click="dataC('1')">tab 1</button>
      <button @click="dataC('2')">tab 2</button>
      <button @click="dataC('3')">tab 3</button>
    </div>
    <component :is="data" />
  </div>
</template>

<style>
button {
  margin: 5px;
}
.switch {
  display: flex;
  gap: 2rem;
}
.switch-btn {
  display: flex;
  flex-direction: column;
}
</style>
