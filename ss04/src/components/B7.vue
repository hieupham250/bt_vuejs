<template>
  <div>
    <input type="number" v-model="inputNumber" @change="handleInputOnChange" />
    <p>Giá trị hiện tại: {{ inputNumber }}</p>
    <p>Giá trị bình phương: {{ catculator }}</p>
  </div>
</template>

<script setup>
import { ref, computed, watch } from "vue";
const inputNumber = ref(1);
const handleInputOnChange = (e) => {
  inputNumber.value = e.target.value;
};

// Computed để tính bình phương của giá trị number
const catculator = computed(() => inputNumber.value ** 2);
watch(catculator, (newValue, oldValue) => {
  console.log(`Giá trị bình phương thay đổi từ ${oldValue} thành ${newValue}`);
});
</script>

<style></style>
