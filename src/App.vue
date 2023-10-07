<template>
  <NavBar />
  <div class="content">
    <router-view />
  </div>
  <FooterItem />
</template>

<script>
import NavBar from "./components/NavBar.vue";
import FooterItem from "./components/FooterItem.vue";

export default {
  components: {
    NavBar,
    FooterItem,
  },
};
</script>

<style lang="scss">
// .content {
//   height: 100%;
// }
</style>
