<template>
  <div>
    <input
      type="text"
      v-model="inputText"
      ref="inputField"
      @keyup.enter="handleKeyUp"
      placeholder="Nhập nội dung và nhấn Shift + Enter"
    />
  </div>
</template>

<script setup>
import { ref } from "vue";
const inputText = ref("");
const inputField = ref(null);

const handleKeyUp = (event) => {
  if (event.shiftKey && event.key === "Enter") {
    if (inputText.value) {
      alert(inputText.value);
      inputText.value = "";
    }
  } else if (event.key === "Enter") {
    alert("Bạn cần nhấn Shift + Enter");
  }
};
</script>

<style></style>
