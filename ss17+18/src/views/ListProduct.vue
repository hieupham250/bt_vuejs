<template>
  <div>
    <h1>List product</h1>
    <form @submit.prevent="searchProduct">
      <input v-model="searchQuery" placeholder="Nhập tên sản phẩm..." />
      <button type="submit">Tìm kiếm</button>
    </form>
    <ul>
      <li v-for="product in filteredProducts" :key="product.id">
        <img :src="product.image" alt="" width="100" />
        <h2>{{ product.name }}</h2>
        <p>{{ product.price }} VND</p>
        <router-link :to="`/product-detail/${product.id}`"
          >Xem chi tiết</router-link
        >
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref, computed, onMounted } from "vue";
import { useRoute, useRouter } from "vue-router";

const products = ref([
  { id: 1, name: "iPhone", price: 20000000, image: "iphone.jpg" },
  { id: 2, name: "Samsung", price: 15000000, image: "samsung.jpg" },
  { id: 3, name: "Vivo", price: 8000000, image: "vivo.jpg" },
  { id: 4, name: "Xiaomi", price: 10000000, image: "xiaomi.jpg" },
]);

const searchQuery = ref("");
const route = useRoute();
const router = useRouter();

onMounted(() => {
  if (!localStorage.getItem("products")) {
    localStorage.setItem("products", JSON.stringify(products.value));
  } else {
    products.value = JSON.parse(localStorage.getItem("products"));
  }

  if (route.query.name) {
    searchQuery.value = route.query.name;
  }
});

const searchProduct = () => {
  router.push(`/list-product?name=${searchQuery.value}`);
};

// Lọc sản phẩm theo query trên URL
const filteredProducts = computed(() => {
  if (route.query.name) {
    return products.value.filter((product) =>
      product.name.toLowerCase().includes(route.query.name.toLowerCase())
    );
  }
  return products.value;
});
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin-bottom: 20px;
}

img {
  display: block;
  margin-bottom: 10px;
}
</style>
