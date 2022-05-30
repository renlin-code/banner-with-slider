<template>
  <article class="news">
    <div class="news__text-container">
      <h1 class="text-container__title">
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
      </h1>
      <p class="text-container__text">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla sit
        impedit saepe consequatur accusamus asperiores.
      </p>
    </div>
    <img
      class="news__image"
      src="../assets/images/news-img-1-mobile.jpg"
      alt="Картинка новости"
    />
  </article>
</template>

<style scoped>
.news {
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: center;
  position: relative;
}
.news__text-container {
  padding: 10px var(--general-padding);
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
  height: 40vh;
  object-fit: cover;
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
