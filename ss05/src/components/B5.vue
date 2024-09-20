<template>
  <div>
    <p>Các số chẵn từ mảng: {{ evenNumbers.join(" ") }}</p>
  </div>
</template>

<script setup>
import { ref } from "vue";
const arr = ref([1, 2, 3, 4, 5, 6, 7, 8, 9, 10]);

const evenNumbers = arr.value.filter((item) => item % 2 === 0);
</script>

<style></style>
