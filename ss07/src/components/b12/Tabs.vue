<template>
  <div class="tabs">
    <div class="tab-headers">
      <TabItem
        v-for="(tab, index) in tabs"
        :key="tab.id"
        :title="tab.title"
        :is-active="activeTab === index"
        @select="selectTab(index)"
      />
    </div>
    <div class="tab-content">
      <slot :active-tab="activeTab" />
    </div>
  </div>
</template>

<script setup>
import { ref, defineProps } from "vue";
import TabItem from "./TabItem.vue";

const props = defineProps({
  tabs: {
    type: Array,
    required: true,
  },
});

const activeTab = ref(0);

const selectTab = (index) => {
  activeTab.value = index;
};
</script>

<style scoped>
.tabs {
  border: 1px solid #ccc;
  border-radius: 5px;
}

.tab-headers {
  display: flex;
  cursor: pointer;
}

.tab-content {
  padding: 10px;
}
</style>
