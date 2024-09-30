<template>
  <div>
    <h1>Dữ liệu trong component con</h1>
    <p>Id: {{ props.product.id }}</p>
    <p>ProductName: {{ props.product.productName }}</p>
    <p>
      Price:
      {{
        props.product.price.toLocaleString("vi", {
          style: "currency",
          currency: "VND",
        })
      }}
    </p>
    <p>Quantity: {{ props.product.quantity }}</p>
  </div>
</template>

<script setup>
const props = defineProps(["product"]);
</script>

<style></style>
