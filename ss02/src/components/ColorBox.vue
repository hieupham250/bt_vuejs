<template>
  <div class="container">
    <div class="div-1">Box</div>
    <div class="div-2">Box</div>
    <div class="div-3">Box</div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.container {
  display: flex;
  gap: 10px;
  margin: 20px 0;
}

.div-1,
.div-2,
.div-3 {
  width: 50px;
  height: 50px;
  text-align: center;
  line-height: 50px;
  color: white;
  font-size: 14px;
}

.div-1 {
  background-color: red;
}

.div-2 {
  background-color: blue;
}

.div-3 {
  background-color: green;
}
</style>
