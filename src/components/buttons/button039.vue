<template>
  <div class="center-center">
    <a class="btn-glitch-fill">
      <span class="text">// Initialize</span
      ><span class="text-decoration">_</span
      ><span class="decoration">&rArr;</span>
    </a>
  </div>
</template>

<script>
// this button is from:
// https://codepen.io/hirodashi/pen/YzGBYBY
export default {
  name: "button39",
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=VT323&display=swap");

body {
  background-color: black;
}

#intro {
  color: white;
  font-family: "VT323", monospace;
}

.center-center {
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%);
}

[class*="btn-glitch-"] {
  display: inline-block;
  font-family: "VT323", monospace;
  border: 1px solid white;
  color: white;
  padding: 10px 13px;
  min-width: 175px;
  line-height: 1.5em;
  white-space: no-wrap;
  text-transform: uppercase;
  cursor: pointer;
  .text,
  .decoration {
    display: inline-block;
  }
  .decoration {
    display: inline-block;
    float: right;
  }
  &:hover,
  &:focus {
    animation-name: glitch;
    animation-duration: 0.2s;
    background-color: yellow;
    color: black;
    border: 1px solid yellow;
    .text-decoration {
      animation-name: blink;
      animation-duration: 0.1s;
      animation-iteration-count: infinite;
    }
    .decoration {
      animation-name: blink;
      animation-duration: 0.1s;
      animation-iteration-count: infinite;
    }
    :before {
      content: " ";
      width: 15px;
      border: 1px solid black;
      position: absolute;
      right: 25%;
      bottom: 3px;
      transform: rotate(35deg);
    }
    :after {
      animation-name: shrink;
      animation-duration: 0.5s;
      animation-iteration-count: 1;
      animation-fill-mode: forwards;
      content: " ";
      width: 75%;
      border: 1px solid black;
      position: absolute;
      left: 0;
      bottom: 5px;
    }
  }
  &:active {
    background: none;
    color: yellow;
    .text-decoration {
      animation-name: none;
    }
    .decoration {
      animation-name: none;
    }
    :before,
    :after {
      display: none;
    }
  }
}

@keyframes glitch {
  25% {
    background-color: red;
    transform: translateX(-10px);
    letter-spacing: 10px;
  }
  35% {
    background-color: green;
    transform: translate(10px);
  }
  59% {
    opacity: 0;
  }
  60% {
    background-color: blue;
    transform: translate(-10px);
    filter: blur(5px);
  }
  100% {
    background-color: yellow;
    blur: (5px);
  }
}

@keyframes blink {
  50% {
    opacity: 0;
  }
}

@keyframes shrink {
  100% {
    width: 10%;
  }
}
</style>
