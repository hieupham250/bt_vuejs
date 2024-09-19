<template>
  <div>
    <ListCourse />
    <ColorBox />
    <Card />
    <Calculation />
    <UserInfo />
    <FormatName />
    <AdminIndex />
    <UserLayout />
  </div>
</template>

<script>
import AdminIndex from "./components/b7/AdminIndex.vue";
import Calculation from "./components/Calculation.vue";
import Card from "./components/Card.vue";
import ColorBox from "./components/ColorBox.vue";
import FormatName from "./components/FormatName.vue";
import ListCourse from "./components/ListCourse.vue";
import UserInfo from "./components/UserInfo.vue";
import UserLayout from "./components/b8/UserLayout.vue";
export default {
  components: {
    ListCourse,
    ColorBox,
    Card,
    Calculation,
    UserInfo,
    FormatName,
    AdminIndex,
    UserLayout,
  },
};
</script>

<style></style>
