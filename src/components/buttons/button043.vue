<template>
  <div class="button"></div>
</template>

<script>
// this button is from:
// https://codepen.io/nocni_sovac/pen/vYGqvJK
export default {
  name: "button43",
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");

body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: #060505;
}

.button {
  border: 2px solid #d2bdff;
  height: 80px;
  width: 200px;
  border-radius: 4px;
  position: relative;
  cursor: pointer;
  font-family: "Roboto", sans-serif;
  margin: 25px;

  &::after {
    content: "HOVER ME";
    position: absolute;
    top: 41%;
    left: 50%;
    transform: translate(-50%);
    color: #d2bdff;
    transition: all 0.1s linear;
  }

  &::before {
    content: "";
    position: relative;
    display: block;
    height: 15px;
    width: 15px;
    background: #d2bdff;
    box-shadow: 0px 0px 10px 3px #0ff;
    margin-left: -8px;
    margin-top: -8px;
    opacity: 0;
    transition: all 0.1s linear;
    border-radius: 100%;
    animation: star 1.3s linear infinite;
  }

  @keyframes star {
    0% {
      margin-left: -8px;
      margin-top: -8px;
    }
    25% {
      margin-left: 194px;
      margin-top: -8px;
    }

    50% {
      margin-left: 194px;
      margin-top: 75px;
    }
    75% {
      margin-left: -8px;
      margin-top: 75px;
    }
    100% {
      margin-left: -8px;
      margin-top: -8px;
    }
  }

  &:hover {
    &::before {
      opacity: 1;
      animation: star 1.3s linear infinite;
    }

    &::after {
      content: "I'M GLOWING";
      text-shadow: 0 0 10px #fff, 0 0 10px #fff, 0 0 20px #82bedc,
        0 0 30px #82bedc, 0 0 40px #82bedc, 0 0 50px #82bedc, 0 0 60px #82bedc;
    }
  }
}
</style> 
