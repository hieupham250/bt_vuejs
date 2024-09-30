<template>
  <div>
    <h1>----- TodoApp Component -----</h1>
    <p>Id to delete: {{ id }}</p>
    <TodoItem @handleDelete="handleDelete"></TodoItem>
  </div>
</template>

<script setup>
import TodoItem from "./TodoItem.vue";
import { ref } from "vue";
const id = ref();

function handleDelete(data) {
  id.value = data;
}
</script>

<style></style>
