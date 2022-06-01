<template>
  <main>
    <!-- <button @click="prev">Prev</button>
    <button @click="next">Next</button> -->
    <div class="main__news-carousel">
      <div class="news-carousel__inner">
        <NewsComp
          v-for="{ id, title, description, url } in allSlides"
          :key="id"
          :id="id"
          :title="title"
          :description="description"
          :url="url"
          :currentSlide="currentSlide"
          :direction="direction"
        />
      </div>
      <CarouselIndicatorsComp
        :total="allSlides.length"
        :currentIndex="currentSlide"
        @switch="switchSlide($event)"
      />
      <KnowMoreComp />
    </div>
  </main>
</template>

<script>
import NewsComp from "./NewsComp.vue";
import CarouselIndicatorsComp from "./CarouselIndicatorsComp.vue";
import KnowMoreComp from "./KnowMoreComp.vue";
export default {
  name: "MainComp",
  data: () => ({
    allSlides: [
      {
        id: 0,
        title: "Техническое обслуживание воздушных судов",
        description:
          "Современные технологии достигли такого уровня, что синтетическое тестирование напрямую зависит от новых предложений. А ещё тщательные исследования конкурентов подвергнуты.",
        url: "https://imgur.com/kZxlaUc.jpg",
      },
      {
        id: 1,
        title: "Новый партнёр отдела технического обслуживания",
        description:
          "В рамках спецификации современных стандартов, независимые государства лишь добавляют фракционных разногласий и объединены в целые кластеры себе подобных.",
        url: "https://imgur.com/S1afPcy.jpg",
      },
      {
        id: 2,
        title: "Набираем в штат более 15 новых специалистов",
        description:
          "С учётом сложившейся международной обстановки, современная методология разработки представляет собой интересный эксперимент проверки экспериментов",
        url: "https://imgur.com/GI0lZam.jpg",
      },
    ],
    currentSlide: 0,
    slideInterval: null,
    direction: "right",
  }),
  methods: {
    setCurrentSlide(index) {
      this.currentSlide = index;
    },
    prev(step = -1) {
      const index =
        this.currentSlide > 0
          ? this.currentSlide + step
          : this.allSlides.length - 1;
      this.setCurrentSlide(index);
      this.direction = "left";
      this.startSlideTimer();
    },
    next(step = 1) {
      const index =
        this.currentSlide < this.allSlides.length - 1
          ? this.currentSlide + +step
          : 0;
      this.setCurrentSlide(index);
      this.direction = "right";
      this.startSlideTimer();
    },
    startSlideTimer() {
      this.stopSlideTimer();
      this.slideInterval = setInterval(() => {
        this.next();
      }, 5000);
    },
    stopSlideTimer() {
      clearInterval(this.slideInterval);
    },
    switchSlide(index) {
      const step = index - this.currentSlide;
      if (step > 0) {
        this.next(step);
      } else {
        this.prev(step);
      }
      this.stopSlideTimer();
    },
  },
  mounted() {
    this.startSlideTimer();
  },
  beforeUnmount() {
    this.stopSlideTimer();
  },
  components: {
    NewsComp,
    KnowMoreComp,
    CarouselIndicatorsComp,
  },
};
</script>

<style scoped>
main {
  width: 100vw;
  height: calc(100vh - 70px);
  margin: 70px auto 0;
  background: var(--white);
}

main .main__news-carousel {
  display: flex;
  justify-content: center;
  position: relative;
}
.main__news-carousel .news-carousel__inner {
  position: relative;
  width: 100vw;
  height: 80vh;
  overflow: hidden;
}
</style>
