<template>
  <div class="containerAdmin">
    <Header />
    <div class="content">
      <Menu />
      <div class="main-footer">
        <Main />
        <Footer />
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./Header.vue";
import Menu from "./Menu.vue";
import Main from "./Main.vue";
import Footer from "./Footer.vue";
export default {
  components: {
    Header,
    Menu,
    Main,
    Footer,
  },
};
</script>

<style>
.containerAdmin {
  display: flex;
  flex-direction: column;
  height: 650px;
}

.content {
  display: flex;
  flex: 1;
}

.main-footer {
  display: flex;
  flex-direction: column;
  flex: 1;
  margin-left: 10px;
}
</style>
