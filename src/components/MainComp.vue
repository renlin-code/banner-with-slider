<template>
  <main>
    <div class="news-wrapper">
      <NewsComp style="width: 100vw" />
    </div>
    <div class="main__slider-buttons-container">
      <SliderButtonComp />
      <SliderButtonComp />
      <SliderButtonComp />
    </div>
    <KnowMoreComp />
  </main>
</template>

<script setup>
import NewsComp from "./NewsComp.vue";
import SliderButtonComp from "./SliderButtonComp.vue";
import KnowMoreComp from "./KnowMoreComp.vue";
</script>

<style scoped>
main {
  width: 100vw;
  height: calc(100vh - 70px);
  margin: 70px auto 0;
  background: var(--white);
}
main .main__slider-buttons-container {
  width: 50vw;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 6px;
  margin: var(--general-padding) 10px 0;
}
</style>
