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
  background-color: black;
  background: rgb(48, 49, 50);
  background-image: radial-gradient(white 1px, transparent 0);
  background-size: 40px 40px;
  background-position: -19px -19px;
}
body {
}
</style>
