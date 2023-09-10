<template>
  <button>Hover for Fun!</button>
</template>

<script>
// this button is from:
// https://codepen.io/ShadowShahriar/pen/XWaLPOv
export default {
  name: "button27",
};
</script>

<style scoped>
/* relevant portion */
button {
  --border-radius: 24px;
  --border-width: 8px;

  appearance: none;
  position: relative;
  padding: 1em 2em;
  border: 0;
  background-color: transparent;
  font-family: "Montserrat", sans-serif;
  font-size: 2em;
  font-weight: 600;
  color: #fff;
}

button::after {
  --m-i: linear-gradient(#000, #000);
  --m-o: content-box, padding-box;

  content: "";
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  padding: var(--border-width);
  border-radius: var(--border-radius);
  background-image: conic-gradient(
    #488cfb,
    #29dbbc,
    #ddf505,
    #ff9f0e,
    #e440bb,
    #655adc,
    #488cfb
  );

  mask-image: var(--m-i), var(--m-i);
  mask-origin: var(--m-o);
  mask-clip: var(--m-o);
  mask-composite: exclude;
  -webkit-mask-composite: destination-out;

  filter: hue-rotate(0);
  animation: hue linear 500ms infinite;
  animation-play-state: paused;
}

button:hover::after {
  animation-play-state: running;
}

@keyframes hue {
  to {
    filter: hue-rotate(1turn);
  }
}

/* to have things in good shape */
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
