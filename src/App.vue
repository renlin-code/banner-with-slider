<template>
  <HomeComp />
</template>

<script>
import HomeComp from "./components/HomeComp.vue";

export default {
  name: "App",
  components: {
    HomeComp,
  },
};
</script>

<style>
:root {
  --dark-blue: #0055a4;
  --blue: #a0cae2;
  --light-blue: #f4f8fa;
  --black: #313131;
  --white: #ffffff;
  --max-width-element: 93%;

  --main-font: "Inter", sans-serif;
  --title-font: "Nexa Demo", sans-serif;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
html {
  font-family: var(--main-font);
  font-size: 62.5%;
}
</style>
