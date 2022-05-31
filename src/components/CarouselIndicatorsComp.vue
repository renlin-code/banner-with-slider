<template>
  <div class="carousel-indicators">
    <button
      class="indicator"
      :class="{ active: currentIndex === index }"
      v-for="(item, index) in total"
      :key="index"
      @click="$emit('switch', index)"
    ></button>
  </div>
</template>

<script>
export default {
  emits: ["switch"],
  props: ["total", "currentIndex"],
};
</script>

<style scoped>
.carousel-indicators {
  width: 50vw;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 6px;
  margin: var(--general-padding) 10px 0;
}

.indicator {
  width: 100%;
  height: 6px;
  border-radius: 6px;
  border: none;
  cursor: pointer;
  background: var(--blue);
}

.active {
  background: var(--dark-blue);
}

@media (min-width: 650px) {
  .carousel-indicators {
    display: none;
  }
}
</style>
