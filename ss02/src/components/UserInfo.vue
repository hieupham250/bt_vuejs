<template>
  <div>
    <h1>Thông tin cá nhân</h1>
    <ul>
      <li>
        Họ và tên: <b>{{ personalInfo.fullName }}</b>
      </li>
      <li>
        Giới tính: <b>{{ personalInfo.gender }}</b>
      </li>
      <li>
        Ngày sinh: <b>{{ personalInfo.dob }}</b>
      </li>
      <li>
        Email: <b>{{ personalInfo.email }}</b>
      </li>
      <li>
        Địa chỉ: <b>{{ personalInfo.address }}</b>
      </li>
    </ul>
  </div>
</template>

<script setup>
const personalInfo = {
  fullName: "Phạm Trung Hiếu",
  gender: "Nam",
  dob: "25/07/2004",
  email: "ptrunghieu2507@gmail.com",
  address: "Thanh Xuân, Hà Nội",
};
</script>

<style></style>
