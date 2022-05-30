<template>
  <div
    @click="burgerCrossed = !burgerCrossed"
    :class="[
      burgerCrossed ? 'main-container--crossed' : 'main-container--no-crossed',
    ]"
    class="main-container"
  >
    <div class="main-container__line main-container__line1"></div>
    <div class="main-container__line main-container__line2"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      burgerCrossed: false,
    };
  },
};
</script>

<style scoped>
.main-container {
  width: 30px;
  height: 100%;
  cursor: pointer;
  position: relative;
}
.main-container .main-container__line {
  width: 30px;
  height: 2px;
  border-radius: 1px;
  display: block;
  position: absolute;
  background-color: var(--black);
  transition: all 300ms;
}

/* STATES CLASSES */
.main-container--no-crossed .main-container__line1 {
  transform: rotate(0deg);
  top: 11px;
}
.main-container--no-crossed .main-container__line2 {
  transform: rotate(0deg);
  top: 17px;
}
.main-container--crossed .main-container__line1 {
  transform: rotate(40deg);
  top: 14.5px;
}
.main-container--crossed .main-container__line2 {
  transform: rotate(-40deg);
  top: 14.5px;
}

@media (min-width: 980px) {
  .main-container {
    display: none;
  }
}
</style>
