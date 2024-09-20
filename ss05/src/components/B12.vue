<template>
  <div>
    <button @click="showNotification">Show notification</button>
    <div v-if="showNotificationState" class="notification">
      <p>Hiển thị thông báo ở đây</p>
      <button class="close-btn" @click="closeNotification">X</button>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const showNotificationState = ref(false);
const showNotification = () => {
  showNotificationState.value = true;
  setTimeout(() => {
    showNotificationState.value = false;
  }, 5000);
};

const closeNotification = () => {
  showNotificationState.value = false;
};
</script>

<style scoped>
.notification {
  position: absolute;
  top: 10px;
  right: 10px;
  background-color: #f8cc07;
  padding: 20px;
  border: 1px solid #f8cc07;
  border-radius: 4px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 250px;
}

.close-btn {
  background: none;
  border: none;
  font-size: 16px;
  cursor: pointer;
}
</style>
