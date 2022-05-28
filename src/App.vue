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
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
