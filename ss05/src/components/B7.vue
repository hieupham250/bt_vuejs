<template>
  <div>
    <button @click="setActive(1)" :class="{ active: activeButton === 1 }">
      button 1
    </button>
    <button @click="setActive(2)" :class="{ active: activeButton === 2 }">
      button 2
    </button>
    <button @click="setActive(3)" :class="{ active: activeButton === 3 }">
      button 3
    </button>
  </div>
</template>

<script setup>
import { ref } from "vue";
const activeButton = ref(1);
const setActive = (buttonNumber) => {
  activeButton.value = buttonNumber;
};
</script>

<style>
.active {
  background-color: red;
  color: white;
}
</style>
