<template>
  <button>
    <h3 class="d-1"><a href="#" onclick="return false;">Hover Me</a></h3>
    <h3 class="d-2"><a href="#" onclick="return false;">Hover Me</a></h3>
  </button>
</template>

<script>
// this button is from:
// https://codepen.io/t_afif/pen/mdXEEmy
export default {
  name: "button21",
};
</script>

<style scoped>
.d-1 {
  --c: #1095c1; /* the color */
  --b: 0.1em; /* border length*/
  --d: 20px; /* the cube depth */
  --h: 1.2em; /* the height */

  --_s: calc(var(--d) + var(--b));

  line-height: var(--h);
  color: #0000;
  text-shadow: 0 calc(-1 * var(--_t, 0em)) var(--c),
    0 calc(var(--h) - var(--_t, 0em)) #fff;
  border: solid #0000;
  overflow: hidden;
  border-width: var(--b) var(--b) var(--_s) var(--_s);
  background: linear-gradient(var(--c) 0 0) 100% 100% /101% var(--_p, 0%) no-repeat,
    conic-gradient(
        at left var(--d) bottom var(--d),
        #0000 90deg,
        rgb(255 255 255 /0.3) 0 225deg,
        rgb(255 255 255 /0.6) 0
      )
      border-box,
    conic-gradient(at left var(--_s) bottom var(--_s), #0000 90deg, var(--c) 0)
      0 100% / calc(100% - var(--b)) calc(100% - var(--b)) border-box;
  transform: translate(calc(var(--d) / -1), var(--d));
  clip-path: polygon(
    var(--d) 0%,
    var(--d) 0%,
    100% 0%,
    100% calc(100% - var(--d)),
    100% calc(100% - var(--d)),
    var(--d) calc(100% - var(--d))
  );
  transition: 0.5s;
}
.d-1:hover {
  transform: translate(0, 0);
  clip-path: polygon(
    0% var(--d),
    var(--d) 0%,
    100% 0%,
    100% calc(100% - var(--d)),
    calc(100% - var(--d)) 100%,
    0% 100%
  );
  --_t: var(--h);
  --_p: 105%;
}

.d-2 {
  --c: #cc333f; /* the color */
  --b: 0.1em; /* border length*/
  --d: 20px; /* the cube depth */
  --h: 1.2em; /* the height */

  --_s: calc(var(--d) + var(--b));
  color: #0000;
  text-shadow: 0 calc(-1 * var(--_t, 0em)) var(--c),
    0 calc(var(--h) - var(--_t, 0em)) #fff;
  border: solid #0000;
  overflow: hidden;
  border-width: var(--b) var(--_s) var(--_s) var(--b);
  background: linear-gradient(var(--c) 0 0) -1px 100% /101% var(--_p, 0%)
      no-repeat,
    conic-gradient(
        from -90deg at right var(--d) bottom var(--d),
        #0000 90deg,
        rgb(255 255 255 /0.3) 0 225deg,
        rgb(255 255 255 /0.6) 0
      )
      border-box,
    conic-gradient(
        at right var(--_s) bottom var(--_s),
        var(--c) 270deg,
        #0000 0
      )
      100% 100% / calc(100% - var(--b)) calc(100% - var(--b)) border-box;
  transform: translate(var(--d), var(--d));
  clip-path: polygon(
    0% 0%,
    calc(100% - var(--d)) 0%,
    calc(100% - var(--d)) 0%,
    calc(100% - var(--d)) calc(100% - var(--d)),
    0 calc(100% - var(--d)),
    0 calc(100% - var(--d))
  );
  transition: 0.5s;
}
.d-2:hover {
  transform: translate(0, 0);
  clip-path: polygon(
    0% 0%,
    calc(100% - var(--d)) 0%,
    100% var(--d),
    100% 100%,
    var(--d) 100%,
    0 calc(100% - var(--d))
  );
  --_t: var(--h);
  --_p: 105%;
}

body {
  height: 100vh;
  margin: 0;
  display: grid;
  grid-template-columns: auto auto;
  gap: 20px;
  place-content: center;
  align-items: center;
}
h3 {
  font-family: system-ui, sans-serif;
  font-size: 3rem;
  margin: 0;
  cursor: pointer;
  padding: 0 0.1em;
}
</style>
