<script setup>
import { ref, h } from "vue";
import Tabs from "./components/ui/Tabs.vue";
import Accordions from "./components/ui/Accordions.vue";
import Count from "./components/ui/Count.vue";
import Range from "./components/ui/Range.vue";
import Cursor from "./components/ui/Cursor.vue";
import Alert from "./components/ui/Alert.vue";
import Card from "./components/ui/Card.vue";
import Fieldset from "./components/ui/Fieldset.vue";
import Drag from "./components/ui/Drag.vue";
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
    case "6":
      data.value = h(Alert);
      break;
    case "7":
      data.value = h(Card);
      break;
    case "8":
      data.value = h(Fieldset);
      break;
    case "9":
      data.value = h(Drag);
      break;
  }
};
</script>

<template>
  <div>
    <div>
      <button @click="dataC('1')">Tabs</button>
      <button @click="dataC('2')">Accordions</button>
      <button @click="dataC('3')">Count</button>
      <button @click="dataC('4')">Range</button>
      <button @click="dataC('5')">Cursor</button>
      <button @click="dataC('6')">Alert</button>
      <button @click="dataC('7')">Card</button>
      <button @click="dataC('8')">Fieldset</button>
      <button @click="dataC('9')">Drag</button>
    </div>

    <component :is="data" />
  </div>
</template>

<style></style>
