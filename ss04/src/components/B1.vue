<template>
  <div>
    <button @click="handleIncrease">click {{ count }} lần</button>
  </div>
</template>

<script setup>
import { ref } from "vue";
const count = ref(0);
const handleIncrease = () => {
  count.value++;
};
</script>

<style></style>
