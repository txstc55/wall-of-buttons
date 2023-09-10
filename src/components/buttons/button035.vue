<template>
  <button class="btn">
    <p>Click Me</p>
  </button>
</template>

<script>
// this button is from:
// https://codepen.io/arnav-dev-git/pen/JjExvEq
export default {
  name: "button35",
};
</script>

<style lang="scss" scoped>
$theme: rgb(0, 0, 0);

.container {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  position: relative;
}

button {
  margin: 0;
  padding: 0;
  border: none;
  outline: none;
  color: inherit;
  // background-color: inherit;
  width: 200px;
  height: 60px;
  cursor: pointer;
  font-size: 16px;
  position: relative;
}

.btn {
  border: 2px solid $theme;
  animation: 0.5s collision ease-in;
  overflow: hidden;
  transition: 0.3s 0.1s;

  &:active {
    transform: translateX(100px);
    background: rgba(255, 255, 255, 0.5);
  }

  p {
    position: relative;
    color: $theme;
    font-weight: 700;
    font-size: 1.2rem;
    z-index: 5;
    transition: 1s ease-in-out;
  }

  &:hover {
    p {
      color: #fff;
    }
  }

  &:before,
  &:after {
    content: "";
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    height: 20px;
    width: 20px;
    border-radius: 50%;
    background-color: $theme;
  }

  &:hover {
    &:before {
      animation: collisionLeft 1s both;
      animation-direction: alternate;
    }
    &:after {
      animation: collisionRight 1s both;
      animation-direction: alternate;
    }
  }

  &:before {
    left: -30%;
  }
  &:after {
    left: 125%;
  }

  @keyframes collisionLeft {
    0% {
      left: -30%;
      width: 20px;
      height: 20px;
    }
    50% {
      left: 50%;
      width: 40px;
      height: 40px;
    }
    100% {
      left: 50%;
      width: 300px;
      height: 300px;
    }
  }

  @keyframes collisionRight {
    0% {
      left: 125%;
      width: 20px;
      height: 20px;
    }
    50% {
      left: 50%;
      width: 40px;
      height: 40px;
    }
    100% {
      left: 50%;
      width: 300px;
      height: 300px;
    }
  }
}

.btn-3 {
  filter: url("#goo");
  border: none;
  background: transparent;
}
</style>
