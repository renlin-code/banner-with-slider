<template>
  <a href="#" class="know-more">
    ЧИТАТЬ ПОДРОБНЕЕ
    <div class="know-more__airplane-radius">
      <span class="airplane-radius__airplane"></span>
    </div>
  </a>
</template>

<style scoped>
.know-more {
  display: grid;
  place-content: center;
  position: absolute;
  right: var(--general-padding);
  bottom: -75px;
  width: 130px;
  height: 130px;
  color: var(--dark-blue);
  font-size: 1.4rem;
  line-height: 1.6rem;
  font-weight: bold;
  text-align: center;
  text-decoration: none;
  border-radius: 50%;
  background: var(--light-blue);
  border: 1.5px solid var(--blue);
}
.know-more:hover {
  background: var(--white);
}
@media (min-width: 650px) {
  .know-more {
    position: absolute;
    left: var(--general-padding);
    bottom: 100px;
    width: 142px;
    height: 142px;
    color: var(--white);
    border: 1.5px solid var(--white);
    font-size: 1rem;
    line-height: 1.2rem;
    background: none;
  }
  .know-more:hover {
    background: none;
  }
  .know-more .know-more__airplane-radius {
    width: 71px;
    height: 20px;
    position: absolute;
    top: calc(50% - 10px);
    left: 50%;
    transition: all 1000ms ease-in-out;
    transform-origin: 0;
  }
  .know-more__airplane-radius .airplane-radius__airplane {
    display: block;
    position: absolute;
    right: -10px;
    top: 0;
    width: 20px;
    height: 20px;
    background-image: url("../assets/icons/airplane.svg");
    background-position: center;
    background-size: contain;
    background-repeat: no-repeat;
  }
  .know-more:hover .know-more__airplane-radius {
    transform: rotate(-360deg);
  }
}
</style>
