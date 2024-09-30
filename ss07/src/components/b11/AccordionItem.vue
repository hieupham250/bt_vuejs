<template>
  <div class="accordion-item">
    <div class="accordion-header" @click="toggle">
      <h3>{{ title }}</h3>
    </div>
    <div v-if="isOpen" class="accordion-body">
      <slot></slot>
    </div>
  </div>
</template>

<script setup>
import { computed } from "vue";

const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  id: {
    type: Number,
    required: true,
  },
  openIds: {
    type: Array,
    default: () => [],
  },
});

const emit = defineEmits(["toggle"]);

const isOpen = computed(() => props.openIds.includes(props.id)); // Kiểm tra nếu ID nằm trong mảng openIds

const toggle = () => {
  emit("toggle", props.id);
};
</script>

<style scoped>
.accordion-item {
  margin-bottom: 10px;
}

.accordion-header {
  background-color: #f1f1f1;
  padding: 10px;
  cursor: pointer;
  border-radius: 5px;
}

.accordion-body {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}
</style>
