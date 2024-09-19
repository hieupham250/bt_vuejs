<template>
  <div class="card">
    <div class="image">Image</div>
    <div class="title">Title</div>
    <button class="button">Add to card</button>
  </div>
</template>

<script>
export default {};
</script>

<style>
.card {
  width: 200px;
  display: flex;
  flex-direction: column;
  border: 1px solid black;
  border-radius: 10px;
}
.image {
  background-color: rgb(167, 167, 167);
  height: 90px;
  text-align: center;
  line-height: 90px;
  color: rgb(83, 83, 83);
  font-size: 14px;
  font-weight: 700;
  border-radius: 10px 10px 0 0;
}
.title {
  height: 50px;
  line-height: 50px;
  text-align: center;
  font-size: 14px;
  font-weight: 700;
}
.button {
  height: 30px;
  margin: 10px;
}
</style>
