<template>
  <button>Button</button>
</template>

<script>
// this button is from:
// https://codepen.io/t_afif/pen/VwxbdpV
export default {
  name: "button10",
};
</script>

<style scoped>
button {
  --b: 3px; /* border thickness */
  --s: 0.15em; /* size of the corner */
  --c: #bd5532;

  padding: calc(0.05em + var(--s)) calc(0.3em + var(--s));
  color: var(--c);
  --_p: var(--s);
  background: conic-gradient(
      from 90deg at var(--b) var(--b),
      #0000 90deg,
      var(--c) 0
    )
    var(--_p) var(--_p) / calc(100% - var(--b) - 2 * var(--_p))
    calc(100% - var(--b) - 2 * var(--_p));
  transition: 0.3s linear, color 0s, background-color 0s;
  outline: var(--b) solid #0000;
  outline-offset: 0.2em;
}
button:hover,
button:focus-visible {
  --_p: 0px;
  outline-color: var(--c);
  outline-offset: 0.05em;
}
button:active {
  background: var(--c);
  color: #fff;
}

body {
  height: 100vh;
  margin: 0;
  display: grid;
  grid-template-columns: auto auto;
  gap: 20px;
  place-content: center;
  background: #daedfb;
}
button {
  font-family: system-ui, sans-serif;
  font-weight: bold;
  font-size: 4rem;
  cursor: pointer;
  border: none;
  margin: 0.1em;
}
</style>
