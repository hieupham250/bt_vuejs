<template>
  <div>
    <ul>
      <li v-if="role == 'admin'">Quyền hạn của bạn là: <b>Admin</b></li>
      <li v-else-if="role == 'user'">Quyền hạn của bạn là: <b>User</b></li>
      <li v-else>Quyền hạn của bạn là: <b>Guest</b></li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";
const role = ref("admin");
</script>

<style></style>
