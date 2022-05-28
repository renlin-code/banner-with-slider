<template>
  <LayoutComp>
    <template #header>
      <HeaderComp />
    </template>
    <template #main>
      <MainComp />
    </template>
  </LayoutComp>
</template>

<script>
import LayoutComp from "./LayoutComp.vue";
import HeaderComp from "./HeaderComp.vue";
import MainComp from "./MainComp.vue";

export default {
  components: {
    LayoutComp,
    HeaderComp,
    MainComp,
  },
};
</script>

<style scoped></style>
