<template>
  <ButtonWall />
</template>

<script>
import ButtonWall from "./components/ButtonWall.vue";

export default {
  name: "App",
  components: {
    ButtonWall,
  },
};
</script>

<style>
html {
  background-color: white;
}
body {
  background-size: 40px 40px;
  background-image: linear-gradient(to right, grey 1px, transparent 1px),
    linear-gradient(to bottom, grey 1px, transparent 1px);
}
</style>
