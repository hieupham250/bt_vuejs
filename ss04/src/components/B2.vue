<template>
  <div>
    <p>Company: {{ company.company }}</p>
    <p>Age: {{ company.age }}</p>
    <button @click="ChandleClickChange">Change data</button>
  </div>
</template>

<script setup>
import { reactive } from "vue";

const company = reactive({
  company: "Rikkei Academy",
  age: 2,
});

const ChandleClickChange = () => {
  company.company = "Rikkei Education";
  company.age = 1;
};
</script>

<style></style>
