<template>
  <div class="head">
    <header>
      <h1>heading</h1>
    </header>
  </div>
  <section>
    <GridPlate />
  </section>
  <FooterItem />
</template>

<script>
import GridPlate from "@/components/GridPlate.vue";
import FooterItem from "@/components/FooterItem.vue";

export default {
  name: "HomeView",
  components: {
    GridPlate,
    FooterItem,
  },
};
</script>

<style lang="scss">
.head {
  display: flex;
}
</style>
