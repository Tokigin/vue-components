<script setup>
import { ref, h } from "vue";
import Tabs from "./components/ui/Tabs.vue";
import Accordions from "./components/ui/Accordions.vue";
import Count from "./components/ui/Count.vue";
import Range from "./components/ui/Range.vue";
import Cursor from "./components/ui/Cursor.vue";
const data = ref(null);
const dataC = (d) => {
  switch (d) {
    case "1":
      data.value = h(Tabs);
      break;
    case "2":
      data.value = h(Accordions);
      break;
    case "3":
      data.value = h(Count);
      break;
    case "4":
      data.value = h(Range);
      break;
    case "5":
      data.value = h(Cursor);
      break;
  }
};

const active = ref(false);
</script>

<template>
  <div>
    <div>
      <button @click="dataC('1')">Tabs</button>
      <button @click="dataC('2')">Accordions</button>
      <button @click="dataC('3')">Count</button>
      <button @click="dataC('4')">Range</button>
      <button @click="dataC('5')">Cursor</button>
    </div>

    <component :is="data" />
  </div>
</template>

<style></style>
