<template>
  <div>
    <form @submit.prevent="handleSubmit" action="">
      <input type="text" />
      <button type="submit">submit</button>
    </form>
  </div>
</template>

<script setup>
const handleSubmit = () => {
  console.log(11111);
};
</script>

<style></style>
