<template>
  <button :type="type" @click="handleClick" class="base-button">
    <slot></slot>
  </button>
</template>

<script setup>
const props = defineProps({
  type: {
    type: String,
    default: "button",
  },
});

const emit = defineEmits(["onclick"]);

const handleClick = () => {
  emit("onclick");
};
</script>

<style scoped>
.base-button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  background-color: #007bff;
  color: white;
  cursor: pointer;
}

.base-button:hover {
  background-color: #0056b3;
}
</style>
