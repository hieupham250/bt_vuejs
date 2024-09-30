<template>
  <div>
    <h1>------ Child Component ------</h1>
    <button @click="handleIncrement">Increment</button>
  </div>
</template>

<script setup>
import { ref } from "vue";
const emit = defineEmits(["handleIncrement"]);
const count = ref(0);

const handleIncrement = () => {
  count.value++;
  emit("handleIncrement", count.value);
};
</script>

<style></style>
