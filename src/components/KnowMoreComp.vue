<template>
  <a href="#" class="know-more">
    ЧИТАТЬ ПОДРОБНЕЕ
    <svg class="know-more__airplane-trail">
      <circle cx="50%" cy="50%" r="71"></circle>
    </svg>
    <span class="know-more__airplane"></span>
  </a>
</template>

<style scoped>
.know-more {
  display: grid;
  place-content: center;
  position: absolute;
  right: var(--general-padding);
  bottom: 0;
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
.know-more__airplane,
.know-more__airplane-trail {
  display: none;
}
@media (min-width: 650px) {
  .know-more {
    position: absolute;
    left: var(--general-padding);
    bottom: 60px;
    width: 142px;
    height: 142px;
    color: var(--white);
    border: 1px solid var(--white);
    font-size: 1rem;
    line-height: 1.2rem;
    background: none;
  }
  .know-more .know-more__airplane {
    display: block;
    position: absolute;
    right: -10.5px;
    top: 61px;
    width: 20px;
    height: 20px;
    background-image: url("../assets/icons/airplane.svg");
    background-position: center;
    background-size: contain;
    background-repeat: no-repeat;
    transition: all 1000ms ease-in-out;
    transform-origin: -61px;
  }
  .know-more .know-more__airplane-trail {
    display: block;
    position: absolute;
    top: -4px;
    left: -4px;
    width: 147px;
    height: 147px;
  }
  .know-more__airplane-trail circle {
    width: 100%;
    height: 100%;
    fill: none;
    stroke-width: 3;
    stroke-linecap: round;
    stroke: var(--blue);
    stroke-dasharray: 445;
    stroke-dashoffset: -445;
    transition: all 1000ms ease-in-out;
  }
  .know-more:hover {
    background: none;
  }
  .know-more:hover .know-more__airplane {
    transform: rotate(-360deg);
  }
  .know-more:hover .know-more__airplane-trail circle {
    stroke-dashoffset: 0;
  }
}
</style>
