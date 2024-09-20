<template>
  <div>
    <button @click="handleRandomNumber">Random Number</button>
    <p>{{ numbers }}</p>
  </div>
</template>

<script setup>
import { ref } from "vue";
const numbers = ref([]);

const handleRandomNumber = () => {
  const randomNumber = Math.floor(Math.random() * 100);
  numbers.value.push(randomNumber);
};
</script>

<style></style>
