<template>
  <main>
    <div class="news-wrapper">
      <NewsComp style="width: 100vw" />
    </div>
    <div class="main__slider-buttons">
      <SliderButtonComp />
      <SliderButtonComp />
      <SliderButtonComp />
    </div>
    <a class="main__know-more"></a>
  </main>
</template>

<script setup>
import NewsComp from "./NewsComp.vue";
import SliderButtonComp from "./SliderButtonComp.vue";
</script>

<style scoped>
main {
  width: 100%;
  height: calc(100vh - 70px);
  margin: 70px auto 0;
  background: var(--white);
}
main .main__slider-buttons {
  width: 50vw;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 6px;
  margin: var(--general-padding) 10px 0;
}
</style>
