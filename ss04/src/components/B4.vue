<template>
  <div style="margin: 20px">
    <input type="text" v-model="inputText" @change="handleInputOnChange" />
  </div>
</template>

<script setup>
import { ref, watch } from "vue";
const inputText = ref("");
const handleInputOnChange = (e) => {
  inputText.value = e.target.value;
};
watch(inputText, (newValue, oldValue) => {
  console.log(`giá trị thay đổi từ "${oldValue}" thành "${newValue}"`);
});
</script>

<style></style>
