<template>
  <div>
    <button @click="handleClick('Rikkei Academy')">Get param</button>
  </div>
</template>

<script setup>
const handleClick = (mess) => {
  console.log(mess);
};
</script>

<style></style>
