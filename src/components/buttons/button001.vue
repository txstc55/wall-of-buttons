<template>
  <a class="button1" href="#" onclick="return false;" style="--color:#1e9bff;">
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    Button
  </a>
</template>

<script>
// this button is from:
// https://codepen.io/mortezasharifinia/pen/QWxmEWW
export default {
  name: "button1",
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@100;300;400;500;600;700;800;900&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}

.button1 {
  position: relative;
  padding: 16px 30px;
  font-size: 1.5rem;
  color: var(--color);
  border: 2px solid rgba(0, 0, 0, 0.5);
  border-radius: 4px;
  text-shadow: 0 0 15px var(--color);
  text-decoration: none;
  text-transform: uppercase;
  letter-spacing: 0.1rem;
  transition: 0.5s;
  z-index: 1;
}

.button1:hover {
  color: #fff;
  border: 2px solid rgba(0, 0, 0, 0);
  box-shadow: 0 0 0px var(--color);
}

.button1::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: var(--color);
  z-index: -1;
  transform: scale(0);
  transition: 0.5s;
}

.button1:hover::before {
  transform: scale(1);
  transition-delay: 0.5s;
  box-shadow: 0 0 10px var(--color),
    0 0 30px var(--color),
    0 0 60px var(--color);
}

.button1 span {
  position: absolute;
  background: var(--color);
  pointer-events: none;
  border-radius: 2px;
  box-shadow: 0 0 10px var(--color),
    0 0 20px var(--color),
    0 0 30px var(--color),
    0 0 50px var(--color),
    0 0 100px var(--color);
  transition: 0.5s ease-in-out;
  transition-delay: 0.25s;
}

.button1:hover span {
  opacity: 0;
  transition-delay: 0s;
}

.button1 span:nth-child(1),
.button1 span:nth-child(3) {
  width: 40px;
  height: 4px;
}

.button1:hover span:nth-child(1),
.button1:hover span:nth-child(3) {
  transform: translateX(0);
}

.button1 span:nth-child(2),
.button1 span:nth-child(4) {
  width: 4px;
  height: 40px;
}

.button1:hover span:nth-child(1),
.button1:hover span:nth-child(3) {
  transform: translateY(0);
}

.button1 span:nth-child(1) {
  top: calc(50% - 2px);
  left: -50px;
  transform-origin: left;
}

.button1:hover span:nth-child(1) {
  left: 50%;
}

.button1 span:nth-child(3) {
  top: calc(50% - 2px);
  right: -50px;
  transform-origin: right;
}

.button1:hover span:nth-child(3) {
  right: 50%;
}

.button1 span:nth-child(2) {
  left: calc(50% - 2px);
  top: -50px;
  transform-origin: top;
}

.button1:hover span:nth-child(2) {
  top: 50%;
}

.button1 span:nth-child(4) {
  left: calc(50% - 2px);
  bottom: -50px;
  transform-origin: bottom;
}

.button1:hover span:nth-child(4 ) {
  bottom: 50%;
}
</style>

