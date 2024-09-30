<template>
  <div>
    <h1>------ Parent Component ------</h1>
    <p>Count: {{ count }}</p>
    <CountChildren @handleIncrement="handleIncrement"></CountChildren>
  </div>
</template>

<script setup>
import CountChildren from "./CountChildren.vue";
import { ref } from "vue";

const count = ref(0);
function handleIncrement(data) {
  count.value = data;
}
</script>

<style></style>
