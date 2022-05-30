<template>
  <header>
    <img
      @click="reload"
      src="@/assets/logos/company-logo.svg"
      alt="Логотип компании"
    />
    <MenuComp :show="showMenu" />
    <BurgerMenuComp @click="showMenu = !showMenu" />
  </header>
</template>

<script>
import MenuComp from "./MenuComp.vue";
import BurgerMenuComp from "./BurgerMenuComp.vue";

export default {
  data() {
    return {
      showMenu: false,
    };
  },
  components: {
    MenuComp,
    BurgerMenuComp,
  },
};
</script>

<style scoped>
header {
  height: 70px;
  width: 100%;
  background-color: var(--white);
  padding: 20px var(--general-padding);
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1;
}
img {
  height: 100%;
  width: 140px;
  cursor: pointer;
  background-color: var(--white);
}
</style>
