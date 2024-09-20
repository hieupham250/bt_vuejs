<template>
  <div>
    <h1>Danh sách bài viết</h1>
    <div
      style="border-bottom: 1px solid black"
      v-for="post in posts"
      :key="post.id"
    >
      <b>id: {{ post.id }}</b> <br />
      <b>title: {{ post.title }}</b
      ><br />
      <b>content: {{ post.content }}</b
      ><br />
      <b>author: {{ post.author }}</b>
    </div>
  </div>
</template>

<script setup>
const posts = [
  {
    id: 1,
    title: "tại sao nên học reactjs",
    content: "học reactjs để đi làm",
    author: "david",
  },
  {
    id: 2,
    title: "props trong reactjs",
    content:
      "props trong reactjs giúp truyền dữ liệu từ component xuống component cha",
    author: "linda",
  },
  {
    id: 3,
    title: "State trong react là gì",
    content: "state giúp trữ trạng thais dữ liệu trong 1 component",
    author: "david",
  },
];
</script>

<style></style>
