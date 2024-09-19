<template>
  <div>
    <h1>Danh sách kết quả</h1>
    <ul>
      <li>{{ num1 }} + {{ num2 }} = {{ result1 }}</li>
      <li>{{ num1 }} - {{ num2 }} = {{ result2 }}</li>
      <li>{{ num1 }} * {{ num2 }} = {{ result3 }}</li>
      <li>{{ num1 }} / {{ num2 }} = {{ result4 }}</li>
    </ul>
  </div>
</template>

<script setup>
const num1 = 10;
const num2 = 10;
const addition = (a, b) => {
  return a + b;
};

const subtraction = (a, b) => {
  return a - b;
};

const multiplication = (a, b) => {
  return a * b;
};

const division = (a, b) => {
  return b != 0 ? a / b : "không thể chia cho 0";
};

const result1 = addition(num1, num2);
const result2 = subtraction(num1, num2);
const result3 = multiplication(num1, num2);
const result4 = division(num1, num2);
</script>

<style></style>
