<template>
  <div>
    <button @click="handleShow">Hiện</button>
    <button @click="handleHidden">Ẩn</button>
    <p v-show="isVisible">Nội dung được hiển thị</p>
  </div>
</template>

<script setup>
import { ref } from "vue";
const isVisible = ref(false);
const handleShow = () => {
  isVisible.value = true;
};
const handleHidden = () => {
  isVisible.value = false;
};
</script>

<style></style>
