<template>
  <div class="container5">
    <a href="#" onclick="return false;"  class="button5">
      <div class="button5__line"></div>
      <div class="button5__line"></div>
      <span class="button5__text">ENTRY</span>
      <div class="button5__drow1"></div>
      <div class="button5__drow2"></div>
    </a>
  </div>
</template>

<script>
// this button is from:
// https://codepen.io/ash_creator/pen/oNyNbNO
export default {
  name: "button7",
};
</script>

<style>
:root {
  /* color type A */
  --line_color: #555555;
  --back_color: #ffecf6;
}

.button5 {
  position: relative;
  z-index: 0;
  width: 240px;
  height: 56px;
  text-decoration: none;
  font-size: 14px;
  font-weight: bold;
  color: var(--line_color);
  letter-spacing: 2px;
  transition: all 0.3s ease;
}
.button5__text {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
}
.button5::before,
.button5::after,
.button5__text::before,
.button5__text::after {
  content: "";
  position: absolute;
  height: 3px;
  border-radius: 2px;
  background: var(--line_color);
  transition: all 0.5s ease;
}
.button5::before {
  top: 0;
  left: 54px;
  width: calc(100% - 56px * 2 - 16px);
}
.button5::after {
  top: 0;
  right: 54px;
  width: 8px;
}
.button5__text::before {
  bottom: 0;
  right: 54px;
  width: calc(100% - 56px * 2 - 16px);
}
.button5__text::after {
  bottom: 0;
  left: 54px;
  width: 8px;
}
.button5__line {
  position: absolute;
  top: 0;
  width: 56px;
  height: 100%;
  overflow: hidden;
}
.button5__line::before {
  content: "";
  position: absolute;
  top: 0;
  width: 150%;
  height: 100%;
  box-sizing: border-box;
  border-radius: 300px;
  border: solid 3px var(--line_color);
}
.button5__line:nth-child(1),
.button5__line:nth-child(1)::before {
  left: 0;
}
.button5__line:nth-child(2),
.button5__line:nth-child(2)::before {
  right: 0;
}
.button5:hover {
  letter-spacing: 6px;
}
.button5:hover::before,
.button5:hover .button5__text::before {
  width: 8px;
}
.button5:hover::after,
.button5:hover .button5__text::after {
  width: calc(100% - 56px * 2 - 16px);
}
.button5__drow1,
.button5__drow2 {
  position: absolute;
  z-index: -1;
  border-radius: 16px;
  transform-origin: 16px 16px;
}
.button5__drow1 {
  top: -16px;
  left: 40px;
  width: 32px;
  height: 0;
  transform: rotate(30deg);
}
.button5__drow2 {
  top: 44px;
  left: 77px;
  width: 32px;
  height: 0;
  transform: rotate(-127deg);
}
.button5__drow1::before,
.button5__drow1::after,
.button5__drow2::before,
.button5__drow2::after {
  content: "";
  position: absolute;
}
.button5__drow1::before {
  bottom: 0;
  left: 0;
  width: 0;
  height: 32px;
  border-radius: 16px;
  transform-origin: 16px 16px;
  transform: rotate(-60deg);
}
.button5__drow1::after {
  top: -10px;
  left: 45px;
  width: 0;
  height: 32px;
  border-radius: 16px;
  transform-origin: 16px 16px;
  transform: rotate(69deg);
}
.button5__drow2::before {
  bottom: 0;
  left: 0;
  width: 0;
  height: 32px;
  border-radius: 16px;
  transform-origin: 16px 16px;
  transform: rotate(-146deg);
}
.button5__drow2::after {
  bottom: 26px;
  left: -40px;
  width: 0;
  height: 32px;
  border-radius: 16px;
  transform-origin: 16px 16px;
  transform: rotate(-262deg);
}
.button5__drow1,
.button5__drow1::before,
.button5__drow1::after,
.button5__drow2,
.button5__drow2::before,
.button5__drow2::after {
  background: var(--back_color);
}
.button5:hover .button5__drow1 {
  animation: drow1 ease-in 0.06s;
  animation-fill-mode: forwards;
}
.button5:hover .button5__drow1::before {
  animation: drow2 linear 0.08s 0.06s;
  animation-fill-mode: forwards;
}
.button5:hover .button5__drow1::after {
  animation: drow3 linear 0.03s 0.14s;
  animation-fill-mode: forwards;
}
.button5:hover .button5__drow2 {
  animation: drow4 linear 0.06s 0.2s;
  animation-fill-mode: forwards;
}
.button5:hover .button5__drow2::before {
  animation: drow3 linear 0.03s 0.26s;
  animation-fill-mode: forwards;
}
.button5:hover .button5__drow2::after {
  animation: drow5 linear 0.06s 0.32s;
  animation-fill-mode: forwards;
}
@keyframes drow1 {
  0% {
    height: 0;
  }
  100% {
    height: 100px;
  }
}
@keyframes drow2 {
  0% {
    width: 0;
    opacity: 0;
  }
  10% {
    opacity: 0;
  }
  11% {
    opacity: 1;
  }
  100% {
    width: 120px;
  }
}
@keyframes drow3 {
  0% {
    width: 0;
  }
  100% {
    width: 80px;
  }
}
@keyframes drow4 {
  0% {
    height: 0;
  }
  100% {
    height: 120px;
  }
}
@keyframes drow5 {
  0% {
    width: 0;
  }
  100% {
    width: 124px;
  }
}

/* 本体には関係ないスタイル */
.container5 {
  width: 100%;
  background-color:white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>


