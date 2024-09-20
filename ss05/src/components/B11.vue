<template>
  <div>
    <h1>Danh sách user</h1>
    <input type="text" v-model="searchQuery" placeholder="Nhập tên user" />
    <button @click="handleSearch">Tìm kiếm</button>
    <ul>
      <li v-for="user in filteredUsers" :key="user.id">{{ user.name }}</li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";

// Danh sách người dùng
const users = ref([
  { id: 1, name: "Alice" },
  { id: 2, name: "Bob" },
  { id: 3, name: "Charlie" },
  { id: 4, name: "Eve" },
]);
const searchQuery = ref("");
const filteredUsers = ref(users.value);

const handleSearch = () => {
  filteredUsers.value = users.value.filter((user) =>
    user.name.toLowerCase().includes(searchQuery.value.toLowerCase())
  );
};
</script>

<style></style>
