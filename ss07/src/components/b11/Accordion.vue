<template>
  <div class="accordion">
    <AccordionItem
      v-for="item in items"
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :open-ids="openIds"
      @toggle="handleToggle"
    >
      <template #default>
        {{ item.content }}
      </template>
    </AccordionItem>
  </div>
</template>

<script setup>
import { ref } from "vue";
import AccordionItem from "./AccordionItem.vue";

const items = ref([
  { id: 1, title: "Mục 1", content: "Nội dung của mục 1" },
  { id: 2, title: "Mục 2", content: "Nội dung của mục 2" },
  { id: 3, title: "Mục 3", content: "Nội dung của mục 3" },
]);

const openIds = ref([]); // Sử dụng mảng để lưu trữ nhiều ID mở

const handleToggle = (id) => {
  if (openIds.value.includes(id)) {
    // Nếu ID đã tồn tại trong mảng thì xóa nó
    openIds.value = openIds.value.filter((openId) => openId !== id);
  } else {
    // Nếu không thì thêm ID vào mảng
    openIds.value.push(id);
  }
};
</script>

<style scoped>
.accordion {
  width: 500px;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 5px;
}
</style>
