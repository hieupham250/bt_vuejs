<template>
  <div>
    <button @click="handleShow">hiện</button>
    <p v-show="isShow">Rikkei Education</p>
  </div>
</template>

<script setup>
import { ref } from "vue";
const isShow = ref(false);
const handleShow = () => {
  isShow.value = true;
};
</script>

<style></style>
