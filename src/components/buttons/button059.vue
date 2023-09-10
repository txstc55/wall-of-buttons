<template>
  <div class="flex">
    <a href="#0" class="bttn">More</a>
  </div>
</template>

<script>
// this button is from:
// https://codepen.io/kitsune/pen/beBJBb
export default {
  name: "button59",
};
</script>

<style lang="scss" scoped>
@import "https://fonts.googleapis.com/css?family=Source+Sans+Pro:700";

$font: "Source Sans Pro", sans-serif;
$primary: #b15947;
$secondary: #f1481b;
$animation: 0.3s all ease;

*,
*::before,
*::after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

a {
  color: #333;
  text-decoration: none;
  transition: $animation;
  &:hover {
    color: $primary;
  }
  &:focus {
    text-decoration: none;
  }
  &:active {
    color: #fff;
  }
}

body {
  padding: 0px 20px;
  margin: 0;
  font-family: $font;
  background: #f4f5ee;
  -webkit-font-smoothing: antialiased;
}

.flex {
  display: flex;
  align-items: center;
  justify-content: center;
}

.bttn {
  width: 100px;
  height: 100px;
  line-height: 100px;
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 2px;
  font-weight: bold;
  position: relative;
  &:after {
    transition: $animation;
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    bottom: 0;
    right: 0;
    border-radius: 3px;
    border: 3px solid $primary;
  }
  &:before {
    content: "";
    position: absolute;
    border-radius: 3px;
    left: 0;
    top: 0;
    bottom: 0;
    right: 0;
    -webkit-transform: rotate(45deg);
    transform: rotate(45deg);
    background: #fff;
    z-index: -1;
  }
  &:hover {
    &:after {
      -webkit-transform: rotate(45deg);
      transform: rotate(45deg);
    }
  }
  &:active {
    -webkit-transform: scale(1.1);
    transform: scale(1.1);
    &:before {
      background-color: $secondary;
    }
    &:after {
      border-color: $secondary;
    }
  }
}
</style>