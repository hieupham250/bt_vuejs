<template>
  <div>
    <p>width = {{ width }}</p>
    <p>height = {{ height }}</p>
    <p>Acreage: {{ acreage }}</p>
    <button @click="handleClickIncreaseWidth">Increase width</button>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
const width = ref(10);
const height = ref(20);
const handleClickIncreaseWidth = () => {
  width.value += 10;
};

const acreage = computed(() => width.value * height.value);
</script>

<style></style>
