<template>
  <div v-if="isOpen" class="form-container">
    <form>
      <div>
        <label for="name">Name:</label>
        <input id="name" type="text" v-model="name" />
      </div>

      <div>
        <label for="email">Email:</label>
        <input id="email" type="email" v-model="email" />
      </div>

      <div>
        <label for="address">Address:</label>
        <input id="address" type="text" v-model="address" />
      </div>

      <button type="button" @click="emitClose">Close</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";
const props = defineProps({
  isOpen: {
    type: Boolean,
    default: false,
  },
});

const emit = defineEmits(["close-form"]);
const emitClose = () => {
  emit("close-form");
};

const name = ref("");
const email = ref("");
const address = ref("");
</script>

<style scoped>
.form-container {
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  max-width: 300px;
  margin-top: 20px;
}
</style>
