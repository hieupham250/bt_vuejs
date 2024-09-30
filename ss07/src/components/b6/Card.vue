<!-- Card.vue -->
<template>
  <div class="card">
    <div class="card-header">
      <slot name="header"> Default Header </slot>
    </div>
    <div class="card-body">
      <slot> Default Body Content </slot>
    </div>
    <div>
      <slot name="footer"> Default Footer </slot>
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
.card {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 16px;
  max-width: 400px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.card-header {
  font-size: 1.5em;
  font-weight: bold;
  margin-bottom: 8px;
}

.card-body {
  margin-bottom: 16px;
}
</style>
