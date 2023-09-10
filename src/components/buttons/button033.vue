<template>
  <button class="button">
    <span class="button-text">Hover me</span>
    <div class="fill-container"></div>
  </button>
</template>

<script>
// this button is from:
// https://codepen.io/gabrielcojea/pen/eYWMPPb
export default {
  name: "button33",
};
</script>

<style lang="scss" scoped>
.button {
  position: relative;
  padding: 24px 64px;
  border-radius: 100vw;
  background-color: transparent;
  font-family: "Playfair Display", serif;
  color: #fafafa;
  border: solid 1px rgba($color: #fafafa, $alpha: 0.3);
  overflow: hidden;
  cursor: pointer;
  transition: all 0.6s cubic-bezier(0.25, 1, 0.5, 1); // easeOutQuart
  -webkit-mask-image: -webkit-radial-gradient(
    white,
    black
  ); // force safari to respect border radius

  .button-text {
    position: relative;
    z-index: 2;
  }

  .fill-container {
    position: absolute;
    left: 0;
    top: 50%;
    width: 100%;
    padding-bottom: 100%;
    transform: translateY(-50%) rotate(180deg);

    // collor filling
    &::after {
      content: "";
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background-color: blue;
      border-radius: 50%;
      transition: all 0.6s cubic-bezier(0.25, 1, 0.5, 1); // easeOutQuart
      transform: translateY(-100%);
    }
  }

  &:hover {
    border-color: blue;
    transform: translateY(-4px);

    .fill-container {
      transform: translateY(-50%) rotate(0);

      &::after {
        transform: translateY(0);
      }
    }
  }
}

html,
body {
  height: 100%;
}

body {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: #1a1a1a;
  color: #fafafa;
  box-sizing: border-box;
  padding: 32px;
}

h1 {
  margin-bottom: 64px;
  font-size: 64px;
  text-align: center;
  max-width: 600px;
}
</style>
