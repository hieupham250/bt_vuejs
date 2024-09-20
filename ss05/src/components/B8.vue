<template>
  <div>
    <button @click="sortAscending">Tăng dần</button>
    <button @click="sortDescending">Giảm dần</button>
    <p>{{ numbers.join(", ") }}</p>
  </div>
</template>

<script setup>
import { ref } from "vue";
const numbers = ref([10, 3, 5, 8, 1, 9, 2, 7, 6, 4]);
const sortAscending = () => {
  numbers.value.sort((a, b) => a - b);
};
const sortDescending = () => {
  numbers.value.sort((a, b) => b - a);
};
</script>

<style></style>
