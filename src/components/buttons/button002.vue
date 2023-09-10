<template>
  <button>Button</button>
</template>

<script>
// this button is from:
// https://codepen.io/t_afif/pen/abKyJNJ
export default {
  name: "button2",
};
</script>

<style scoped>
button {
  --c: #229091; /* the color*/

  box-shadow: 0 0 0 0.1em inset var(--c);
  --_g: linear-gradient(var(--c) 0 0) no-repeat;
  background: var(--_g) calc(var(--_p, 0%) - 100%) 0%,
    var(--_g) calc(200% - var(--_p, 0%)) 0%,
    var(--_g) calc(var(--_p, 0%) - 100%) 100%,
    var(--_g) calc(200% - var(--_p, 0%)) 100%;
  background-size: 50.5% calc(var(--_p, 0%) / 2 + 0.5%);
  outline-offset: 0.1em;
  transition: background-size 0.4s, background-position 0s 0.4s;
}
button:hover {
  --_p: 100%;
  transition: background-position 0.4s, background-size 0s;
}
button:active {
  box-shadow: 0 0 9e9Q inset #0009;
  background-color: var(--c);
  color: #fff;
}

body {
  height: 100vh;
  margin: 0;
  display: grid;
  place-content: center;
  grid-auto-flow: column;
  gap: 40px;
  background: #f2dca2;
}
button {
  font-family: system-ui, sans-serif;
  font-size: 3.5rem;
  cursor: pointer;
  padding: 0.1em 0.6em;
  font-weight: bold;
  border: none;
}
</style>