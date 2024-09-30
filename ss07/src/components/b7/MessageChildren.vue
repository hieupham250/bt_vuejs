<template>
  <div>
    <button @click="sendMessage">Send message</button>
  </div>
</template>

<script setup>
const emit = defineEmits(["handleMessage"]);
const sendMessage = () => {
  emit("message-sent", "Nút đã được nhấn từ component con");
};
</script>
