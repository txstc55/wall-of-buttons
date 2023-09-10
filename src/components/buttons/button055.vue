<template>
  <button class="space-btn">Spacy Button</button>
</template>

<script>
// this button is from:
// https://codepen.io/Azragh/pen/GGwQvB
export default {
  name: "button55",
};
</script>

<style lang="scss" scoped>
@import url(https://fonts.googleapis.com/css?family=Electrolize);

$btn-color: #ffb902;

* {
  box-sizing: border-box;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #111;
}

.space-btn {
  position: relative;
  font-family: "Electrolize", sans-serif;
  font-size: 1em;
  text-transform: uppercase;
  letter-spacing: 0.125em;
  line-height: 1;
  color: $btn-color;
  margin: 0;
  padding: 1em;
  background: none;
  border: none;
  cursor: pointer;

  &:hover {
    color: lighten($btn-color, 20%);
  }
  &:focus {
    color: lighten($btn-color, 10%);
    outline: none;
  }
  &:active {
    color: $btn-color;
  }

  &:before,
  &:after {
    content: "";
    display: block;
    position: absolute;
    width: 100%;
    height: 1px;
  }

  &:before {
    top: 0;
    left: 0;
    box-shadow: inset 1px 1px 0 0 $btn-color;
  }
  &:after {
    right: 0;
    bottom: 0;
    box-shadow: inset -1px -1px 0 0 $btn-color;
  }
}

.space-btn:hover {
  &:before {
    animation: hoverShadowBefore 1s forwards;
  }
  &:after {
    animation: hoverShadowAfter 1s forwards;
  }
}

@keyframes hoverShadowBefore {
  0% {
    width: 100%;
    height: 1px;

    top: 0;
    left: 0;
  }
  33% {
    width: 1px;
    height: 100%;

    top: 0;
    left: 0;
  }
  66% {
    width: 1px;
    height: 1px;

    top: calc(100% - 1px);
    left: 0;
  }
  100% {
    width: 100%;
    height: 1px;

    top: calc(100% - 1px);
    left: 0;
  }
}

@keyframes hoverShadowAfter {
  0% {
    width: 100%;
    height: 1px;
  }
  33% {
    width: 1px;
    height: 100%;

    bottom: 0;
    right: 0;
  }
  66% {
    width: 1px;
    height: 1px;

    bottom: calc(100% - 1px);
    right: 0;
  }
  100% {
    width: 100%;
    height: 1px;

    bottom: calc(100% - 1px);
    right: 0;
  }
}
</style>