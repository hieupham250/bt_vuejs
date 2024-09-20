<template>
  <div>
    <img :src="url" alt="" style="width: 300px; height: 200px" />
    <button @click="handleChangeImage">Change image</button>
  </div>
</template>

<script setup>
import { ref } from "vue";
const urls = [
  "https://png.pngtree.com/thumb_back/fh260/background/20230408/pngtree-powder-smoke-colorful-background-image_2164096.jpg",
  "https://w0.peakpx.com/wallpaper/1004/268/HD-wallpaper-vector-art-flowers-background-jpg-neon-flowers-clear-blue-thumbnail.jpg",
  "https://png.pngtree.com/thumb_back/fh260/background/20230408/pngtree-rainbow-curves-abstract-colorful-background-image_2164067.jpg",
  "https://static.vecteezy.com/system/resources/thumbnails/023/669/545/small/abstract-gradient-pink-blue-liquid-wave-background-free-vector.jpg",
];
const url = ref(urls[0]);

const handleChangeImage = () => {
  const randomIndex = Math.floor(Math.random() * urls.length);
  url.value = urls[randomIndex];
};
</script>

<style></style>
