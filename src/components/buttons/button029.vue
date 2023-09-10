<template>
  <button class="button-background-move" role="button">Background Move</button>
</template>

<script>
// this button is from:
// https://codepen.io/fabiocberg/pen/wvqpXqg
export default {
  name: "button29",
};
</script>

<style scoped>
/* CONTAINER */

/* BUTTON GLITCH */
/* BACKGROUND MOVE */
.button-background-move {
  font-size: 16px;
  font-weight: 200;
  letter-spacing: 1px;
  padding: 13px 20px 13px;
  outline: 0;
  border: 1px solid black;
  cursor: pointer;
  position: relative;
  background-color: rgba(0, 0, 0, 0);
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.button-background-move:after {
  content: "";
  background-color: #ffe54c;
  width: 100%;
  z-index: -1;
  position: absolute;
  height: 100%;
  top: 7px;
  left: 7px;
  transition: 0.2s;
}

.button-background-move:hover:after {
  top: 0px;
  left: 0px;
}

@media (min-width: 768px) {
  .button-background-move {
    padding: 13px 50px 13px;
  }
}
</style>
