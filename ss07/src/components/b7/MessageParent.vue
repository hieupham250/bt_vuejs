<template>
  <div>
    <MessageChildren @message-sent="handleMessage" />
  </div>
</template>

<script setup>
import MessageChildren from "./MessageChildren.vue";

const handleMessage = (message) => {
  alert(message);
};
</script>
