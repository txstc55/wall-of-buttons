<template>
  <button class="noselect"></button>
</template>

<script>
// this button is from:
// https://codepen.io/chancesq/pen/bGpddXE
export default {
  name: "button47",
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
  background-color: #1b2845;
  background-image: linear-gradient(315deg, #1b2845 0%, #274060 74%);
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

button {
  width: 150px;
  height: 50px;
  cursor: pointer;
  border: none;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #7f5a83;
  background-image: linear-gradient(315deg, #7f5a83 0%, #0d324d 74%);
  background-size: 200% 100%;
  background-position: left;
  background-repeat: no-repeat;
  transition: 500ms;
}

button:before {
  content: "Brighten";
  color: rgba(255, 255, 255, 0.5);
  font-size: 16px;
  position: absolute;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 140px;
  height: 40px;
  background-color: #1b2845;
  background-image: linear-gradient(315deg, #1b2845 0%, #274060 74%);
  transition: 500ms;
}

button:hover {
  background-position: right;
}

button:hover:before {
  color: rgba(255, 255, 255, 0.8);
}

button:focus {
  outline: none;
}
</style>