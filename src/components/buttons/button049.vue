<template>
  <a href="#" onclick="return false">
    <link
      href="https://fonts.googleapis.com/css2?family=Play:wght@700&display=swap"
      rel="stylesheet"
    />

    <button class="noselect"></button>
  </a>
</template>

<script>
// this button is from:
// https://codepen.io/chancesq/pen/QWyxZGr
export default {
  name: "button49",
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  height: 100vh;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #000000;
  background-image: linear-gradient(315deg, #000000 0%, #414141 74%);
}

.noselect {
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
}

button,
button:before {
  display: flex;
  align-items: center;
  justify-content: center;
}

button {
  width: 150px;
  height: 50px;
  cursor: pointer;
  font-family: "Play", sans-serif;
  font-size: 20px;
  color: white;
  border: none;
  border-radius: 25px;
  background-image: url("https://assets.codepen.io/3305358/hazard-stripes-wallpaper.jpg");
  background-size: 150%;
  background-position: left;
  transition: 1s;
}

button:before {
  width: 150px;
  height: 50px;
  content: "Hazard";
  background: rgba(0, 0, 0, 0.6);
  border-radius: 25px;
  position: absolute;
  transition: 500ms;
}

button:hover:before {
  background: rgba(0, 0, 0, 0);
  text-shadow: 1px 1px 1px black;
}

button:hover {
  background-position: center;
  box-shadow: 0px 0px 10px rgba(232, 218, 26, 0.5);
}

button:focus {
  outline: none;
}
</style>