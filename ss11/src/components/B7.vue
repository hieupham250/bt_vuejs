<template>
  <div>
    <input type="text" v-model="inputValue" />
  </div>
</template>

<script setup>
import { ref, onUpdated } from "vue";

const inputValue = ref("");

onUpdated(() => {
  document.title = inputValue.value;
});
</script>

<style></style>
