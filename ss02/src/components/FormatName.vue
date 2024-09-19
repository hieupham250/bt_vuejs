<template>
  <div>
    <b>Họ và tên: {{ fullName }}</b>
  </div>
</template>

<script setup>
import { ref } from "vue";

const user = {
  firstName: "Phạm Trung",
  lastName: "Hiếu",
};

const formatName = (user) => {
  return `${user.firstName} ${user.lastName}`;
};

const fullName = ref(formatName(user));
</script>

<style></style>
