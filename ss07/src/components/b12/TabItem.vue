<template>
  <div class="tab-item" :class="{ active: isActive }" @click="handleClick">
    {{ title }}
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from "vue";

const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  isActive: {
    type: Boolean,
    default: false,
  },
});

const emit = defineEmits(["select"]);

const handleClick = () => {
  emit("select");
};
</script>

<style scoped>
.tab-item {
  padding: 10px;
  background-color: #f1f1f1;
  border-bottom: 2px solid transparent;
}

.tab-item.active {
  color: blue;
  border-bottom-color: blue;
  font-weight: bold;
}
</style>
