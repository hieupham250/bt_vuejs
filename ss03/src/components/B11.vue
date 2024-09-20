<template>
  <div>
    <div :class="['box', isActive ? 'active' : '']"></div>
    <button @click="handleChangeBg">Change background</button>
  </div>
</template>

<script setup>
import { ref } from "vue";
const isActive = ref(false);

const handleChangeBg = () => {
  isActive.value = !isActive.value;
};
</script>

<style>
.box {
  margin: 20px;
  width: 100px;
  height: 100px;
  background-color: red;
}

.active {
  background-color: blue;
}
</style>
