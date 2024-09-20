<template>
  <div>
    <h1>Gender: {{ gender }}</h1>
    <button @click="handleRandomGender">Random Gender</button>
  </div>
</template>

<script setup>
import { ref } from "vue";
const genders = ["Nam", "Nữ", "Khác"];
const gender = ref(genders[0]);

const handleRandomGender = () => {
  const randomIndex = Math.floor(Math.random() * genders.length);
  gender.value = genders[randomIndex];
};
</script>

<style></style>
