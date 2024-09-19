<template>
  <div class="containerUser">
    <Header />
    <Navigation />
    <div class="content">
      <Menu />
      <MainUser />
      <Article />
    </div>
  </div>
</template>

<script>
import Header from "./Header.vue";
import Navigation from "./Navigation.vue";
import Menu from "./Menu.vue";
import MainUser from "./MainUser.vue";
import Article from "./Article.vue";

export default {
  components: {
    Header,
    Navigation,
    Menu,
    MainUser,
    Article,
  },
};
</script>

<style>
.containerUser {
  height: 500px;
}
</style>
