<template>
  <div>
    <h1>------ Child Component ------</h1>
    <p>Child Company: {{ props.company }}</p>
  </div>
</template>

<script setup>
const props = defineProps(["company"]);
</script>

<style></style>
