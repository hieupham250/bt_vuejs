<template>
  <div>
    <h1>----- TodoItem Component -----</h1>
    <button @click="handleDelete">Delete</button>
  </div>
</template>

<script setup>
import { ref } from "vue";
const emit = defineEmits(["handleDelete"]);
const id = ref(1);

const handleDelete = () => {
  emit("handleDelete", id.value);
};
</script>

<style></style>
