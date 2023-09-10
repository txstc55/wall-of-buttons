<template>
  <button class="name noselect">BoxShadow</button>
</template>

<script>
// this button is from:
// https://codepen.io/chancesq/pen/xxVGbrw
export default {
  name: "button46",
};
</script>

<style scoped>

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
  font-size: 20px;
  font-weight: bold;
  color: black;
  background: white;
  border: 2px solid black;
  box-shadow: 5px 5px 0 black, -5px -5px 0 black, -5px 5px 0 black,
    5px -5px 0 black;
  transition: 500ms ease-in-out;
}

button:hover {
  box-shadow: 20px 5px 0 black, -20px -5px 0 black;
}

button:focus {
  outline: none;
}
</style>