<template>
  <div>
    <input type="text" :disabled="isDisable" :value="isDisable ? '' : value" />
  </div>
</template>

<script setup>
const isDisable = true;
const value = "cho phép nhập";
</script>

<style></style>
