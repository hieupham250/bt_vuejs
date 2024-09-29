<template>
  <div class="container">
    <form id="todo-form" @submit="handleCreated">
      <input
        v-model="valueInput"
        type="text"
        id="todo-input"
        placeholder="Nhập công việc mới..."
        required
      />
      <button type="submit">Add Job</button>
    </form>
    <ul id="todo-list">
      <li v-for="job in listJobs" :key="job.id">
        <input
          @click="handleClick(job.id)"
          type="checkbox"
          v-model="job.status"
        />
        <p :style="{ textDecoration: job.status ? 'line-through' : 'none' }">
          {{ job.name }}
        </p>
        <button @click="handleDelete(job.id)" class="delete-btn">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref, watch } from "vue";

const valueInput = ref("");

const data = [
  { id: 1, name: "Code", status: false },
  { id: 2, name: "Review code", status: true },
  { id: 3, name: "Test application", status: false },
  { id: 4, name: "Fix bugs", status: true },
  { id: 5, name: "Deploy project", status: false },
];

if (!localStorage.getItem("data")) {
  localStorage.setItem("data", JSON.stringify(data));
}

const listJobs = ref(JSON.parse(localStorage.getItem("data")));

const handleDelete = (id) => {
  listJobs.value = listJobs.value.filter((job) => job.id !== id);
};

const handleCreated = (event) => {
  event.preventDefault();
  if (valueInput.value.trim() === "") return;

  const newJob = {
    id: listJobs.value.length
      ? listJobs.value[listJobs.value.length - 1].id + 1
      : 1,
    name: valueInput.value,
    status: false,
  };
  listJobs.value.push(newJob);
  valueInput.value = "";
};

const handleClick = (id) => {
  const job = listJobs.value.find((job) => job.id === id);
  if (job) {
    job.status = !job.status;
    localStorage.setItem("data", JSON.stringify(listJobs.value));
  }
};
</script>

<style>
.container {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

#todo-form {
  width: 500px;
  display: flex;
  gap: 10px;
}

#todo-input {
  padding: 10px;
  width: 80%;
}

#todo-form button {
  width: 18%;
  background-color: white;
  border: 1px solid gray;
}

ul {
  width: 500px;
  list-style-type: none;
  padding: 0;
}

ul li {
  padding: 10px;
  margin-bottom: 5px;
  display: flex;
  align-items: center;
}

ul li p {
  flex-grow: 1;
  margin: 0 10px;
}

.delete-btn {
  background-color: red;
  color: white;
  padding: 10px;
  border: none;
}
</style>
