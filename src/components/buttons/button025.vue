<template>
  <div class="d-1">Hover me</div>
</template>

<script>
// this button is from:
// https://codepen.io/t_afif/pen/GRvEjeM
export default {
  name: "button25",
};
</script>

<style scoped>
.d-1 {
  --b: 4px; /* border length*/
  --c: 20px; /* the cube perspective */

  --g: calc(var(--c) * 0.707); /* 0.707 = cos(45deg) = sin(45deg) */

  padding: 8px;
  transition: 0.5s;
  border: solid transparent;
  border-width: var(--b) var(--b) calc(var(--c) + var(--b))
    calc(var(--c) + var(--b));
  background: linear-gradient(
        -45deg,
        transparent var(--g),
        rgba(255, 255, 255, 0.6) 0
      )
      left / var(--c) 100%,
    linear-gradient(135deg, transparent var(--g), rgba(255, 255, 255, 0.3) 0)
      bottom / 100% var(--c),
    conic-gradient(
      from -90deg at top var(--b) right var(--b),
      currentColor 270deg,
      transparent 0
    ),
    conic-gradient(
      from 90deg at bottom calc(var(--c) + var(--b)) left
        calc(var(--c) + var(--b)),
      currentColor 270deg,
      transparent 0
    );
  background-repeat: no-repeat;
  background-origin: border-box;
  transform: translate(calc(var(--c) / -1), calc(var(--c) / 1));
  clip-path: polygon(
    var(--c) 0%,
    var(--c) 0%,
    100% 0%,
    100% calc(100% - var(--c)),
    100% calc(100% - var(--c)),
    var(--c) calc(100% - var(--c)),
    var(--c) calc(100% - var(--c))
  );
}
.d-1:hover {
  transform: translate(0, 0);
  clip-path: polygon(
    0% var(--c),
    var(--c) 0%,
    100% 0%,
    100% calc(100% - var(--c)),
    calc(100% - var(--c)) 100%,
    0% 100%,
    0% 100%
  );
}

/**/
div[class] {
  display: inline-block;
  font-size: 40px;
  font-family: sans-serif;
  margin: 25px;
  cursor: pointer;
}

body {
  text-align: center;
}
</style>
