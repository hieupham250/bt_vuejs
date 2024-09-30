<template>
  <div>
    <ParentComponent></ParentComponent>
    <ProductParent></ProductParent>
    <CountParent></CountParent>
    <TodoApp></TodoApp>
    <Modal>
      <template #header>
        <h2>Thông báo từ hệ thống</h2>
      </template>
      <template #body>
        <p>
          Đây là nội dung của modal. Bạn có thể đóng modal bằng cách nhấn vào
          nút 'Close'.
        </p>
      </template>
    </Modal>
    <Card>
      <template #header>
        <h2>Thông tin sản phẩm</h2>
      </template>
      <template #default>
        <p>
          Đây là mô tả ngắn gọn về sản phẩm này. Sản phẩm có các tính năng nổi
          bật và giá cả hợp lý.
        </p>
      </template>
      <template #footer>
        <button @click="handleClick">Xem chi tiết</button>
      </template>
    </Card>
    <MessageParent></MessageParent>
    <ListUser></ListUser>
    <BaseButton type="submit" @onclick="handleSubmit">Submit</BaseButton>
    <BaseButton type="button" @onclick="handleCancel">Cancel</BaseButton>
    <BaseButton type="reset" @onclick="handleReset">Reset</BaseButton>
    <AccordionItem></AccordionItem>
    <Tabs :tabs="tabs">
      <template #default="{ activeTab }">
        <div v-if="activeTab === 0">Item one</div>
        <div v-if="activeTab === 1">Item two</div>
        <div v-if="activeTab === 2">Item three</div>
      </template>
    </Tabs>
  </div>
</template>

<script setup>
import ParentComponent from "./components/b1/ParentComponent.vue";
import ProductParent from "./components/b2/ProductParent.vue";
import CountParent from "./components/b3/CountParent.vue";
import TodoApp from "./components/b4/TodoApp.vue";
import Modal from "./components/b5/Modal.vue";
import Card from "./components/b6/Card.vue";
import MessageParent from "./components/b7/MessageParent.vue";
import ListUser from "./components/b8/ListUser.vue";
import BaseButton from "./components/b9/BaseButton.vue";
import AccordionItem from "./components/b11/Accordion.vue";
import Tabs from "./components/b12/Tabs.vue";

import { ref } from "vue";

const tabs = ref([
  { id: 1, title: "Tab 1" },
  { id: 2, title: "Tab 2" },
  { id: 3, title: "Tab 3" },
]);

const handleSubmit = () => {
  console.log("Submit ");
};

const handleCancel = () => {
  console.log("Cancel ");
};

const handleReset = () => {
  console.log("Reset ");
};
</script>

<style></style>
