<template>
  <div>
    <h1>------ Parent Component ------</h1>
    <p>Parent Company: Rikkei Academy</p>
    <ChildrenComponent :company="company"></ChildrenComponent>
  </div>
</template>

<script setup>
import ChildrenComponent from "./ChildrenComponent.vue";

const company = "Rikkei Academy";
</script>

<style></style>
