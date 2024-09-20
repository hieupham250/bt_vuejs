<template>
  <div>
    <div :class="['div', isActive ? 'active' : '']">Block</div>
  </div>
</template>

<script setup>
const isActive = true;
</script>

<style>
.div {
  margin: 20px 0;
  padding: 10px;
  background-color: blue;
  color: black;
}
.active {
  background-color: red;
  color: white;
}
</style>
