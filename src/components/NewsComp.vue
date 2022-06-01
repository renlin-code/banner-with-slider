<template>
  <transition :name="transitionEffect">
    <article class="news" v-show="currentSlide === id">
      <div class="news__text-container">
        <h1 class="text-container__title">{{ title }}</h1>
        <p class="text-container__text">{{ description }}</p>
      </div>
      <img class="news__image" :src="url" alt="Картинка новости" />
    </article>
  </transition>
</template>

<script>
export default {
  props: ["id", "title", "description", "url", "currentSlide", "direction"],
  computed: {
    transitionEffect() {
      return this.direction === "right" ? "slide-in" : "slide-out";
    },
  },
};
</script>
<style scoped>
.news {
  margin: 0 auto;
  display: flex;
  width: 100vw;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  gap: 6px;
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}
.news__text-container {
  padding: 10px var(--general-padding);
  height: 50%;
}
.news__text-container .text-container__title {
  font-family: var(--title-font);
  font-size: 3.2rem;
  line-height: 3.6rem;
}
.news__text-container .text-container__text {
  font-size: 1.6rem;
  line-height: 2.1rem;
  padding: 20px 0;
}
.news .news__image {
  display: block;
  width: 100%;
  height: 30vh;
  object-fit: cover;
}

.slide-in-enter-active,
.slide-in-leave-active,
.slide-out-enter-active,
.slide-out-leave-active {
  transition: all 1s ease-in-out;
}
.slide-in-enter-from {
  transform: translateX(100%);
}
.slide-in-leave-to {
  transform: translateX(-100%);
}
.slide-out-enter-from {
  transform: translateX(-100%);
}
.slide-out-leave-to {
  transform: translateX(100%);
}

@media (min-width: 650px) {
  .news__text-container {
    position: absolute;
    top: 70px;
    left: 0;
    color: var(--white);
  }
  .news__text-container .text-container__title {
    width: 70vw;
  }
  .news__text-container .text-container__text {
    width: 50vw;
  }
  .news .news__image {
    height: 80vh;
    width: 100%;
  }
}
</style>
