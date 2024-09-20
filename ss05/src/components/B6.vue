<template>
  <div>
    <p>
      Các số thỏa mãn điều kiện từ mảng: {{ satisfactoryNumbers.join(" ") }}
    </p>
  </div>
</template>

<script setup>
import { ref } from "vue";
const arr = ref([5, 12, 15, 22, 9, 18, 25, 30, 7, 33]);

const satisfactoryNumbers = arr.value.filter((item) => item % 2 === 0);
</script>

<style></style>
