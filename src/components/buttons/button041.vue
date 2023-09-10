<template>
  <a href="javascript:void(0);" class="pixel-button41">Pixel button</a>
</template>

<script>
// this button is from:
// https://codepen.io/martinboykov/pen/jOrEWBr
export default {
  name: "button41",
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700;800;900&display=swap");

:root {
  --color-red: #ec1840;
  --color-purple: #7a18ec;
  --color-white: #fff;
  --color-black-1: #111;
  --color-black-2: #222;
  --color-black-3: #444;
  --speed-normal: 0.5s;
  --speed-fast: 0.8s;
}

.pixel-button41 {
  position: relative;
  width: 180px;
  height: 60px;
  margin: 20px;
  padding: 10px;
  line-height: 60px;
  letter-spacing: 2px;
  text-decoration: none;
  text-transform: uppercase;
  text-align: center;
  color: var(--color-white);
  trasnition: var(--speed-normal);
  border: 1px solid var(--color-red);
  &:hover {
    border: 1px solid transparent;
    background: var(--color-red) url(https://i.postimg.cc/wBXGXbWN/pixel.png); // 360px x 1080px
    transition-delay: 0.8s;
    background-size: 180px;
    animation: animate41 var(--speed-fast) steps(8) forwards;
  }
  &:last-of-type {
    border: 1px solid var(--color-purple);
    &:hover {
      background: var(--color-purple)
        url(https://i.postimg.cc/FzBWFtKM/pixel2.png); // 360px x 1080px
    }
  }
}
@keyframes animate41 {
  0% {
    background-position-y: 0;
  }
  100% {
    background-position-y: -480px;
  }
}
</style>
