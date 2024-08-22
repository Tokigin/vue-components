<script setup>
import { ref } from "vue";
const open = ref(false);
defineProps({
  title: {
    default: "Lorem ipsum dolor",
    type: String,
  },
});
</script>
<template>
  <div>
    <div class="head" @click="open = !open">
      <h3>{{ title }}</h3>
      <div :class="open ? 'rotate' : ''">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="icon icon-tabler icons-tabler-outline icon-tabler-chevron-right"
        >
          <path stroke="none" d="M0 0h24v24H0z" fill="none" />
          <path d="M9 6l6 6l-6 6" />
        </svg>
      </div>
    </div>

    <div v-if="open">
      <slot></slot>
    </div>
    <div v-else></div>
  </div>
</template>

<style scoped>
.head {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
.rotate {
  rotate: 90deg;
}
</style>
