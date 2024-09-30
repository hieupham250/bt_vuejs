<template>
  <div>
    <ProductChildren :product="product"></ProductChildren>
  </div>
</template>

<script setup>
import ProductChildren from "./ProductChildren.vue";

const product = {
  id: 1,
  productName: "Bưởi ba Roi",
  price: 12000,
  quantity: 10,
};
</script>

<style></style>
