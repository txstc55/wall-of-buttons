<template>
  <a href="#" onclick="return false;">Hover Me</a>
</template>

<script>
// this button is from:
// https://codepen.io/imanirudh1/pen/PoNrLdP
export default {
  name: "button42",
};
</script>

<style scoped>
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: rgb(58, 56, 56);
}
a {
  text-decoration: none;
  border: 3px solid yellow;
  color: transparent;
  padding: 40px 80px;
  font-size: 28px;
  font-family: sans-serif;
  letter-spacing: 5px;
  transition: all 0.5s;
  position: relative;
}
a:before {
  content: "Hover Me";
  display: flex;
  justify-content: center;
  align-items: center;
  color: yellow;
  background: rgb(34, 34, 34);
  font-size: 28px;
  top: 0;
  left: 100%;
  font-family: sans-serif;
  letter-spacing: 5px;
  transition: all 1s;
  height: 100%;
  width: 100%;
  position: absolute;
  transform: scale(0) rotatey(0);
  opacity: 0;
}
a:hover:before {
  transform: scale(1) rotatey(360deg);
  left: 0;
  opacity: 1;
}
a:after {
  content: "Hover Me";
  display: flex;
  justify-content: center;
  align-items: center;
  color: yellow;
  background: rgb(34, 34, 34);
  font-size: 28px;
  top: 0;
  left: 0;
  font-family: sans-serif;
  letter-spacing: 5px;
  transition: all 1s;
  height: 100%;
  width: 100%;
  position: absolute;
  transform: scale(1) rotatey(0);
  opacity: 1;
}
a:hover:after {
  transform: scale(0) rotatey(360deg);
  left: -100%;
  opacity: 0;
}
</style>
