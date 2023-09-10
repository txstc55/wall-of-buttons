<template>
  <button>
    <span>hover me</span>
  </button>
</template>

<script>
// this button is from:
// https://codepen.io/Danil89/pen/MzrEdX
export default {
  name: "button53",
};
</script>

<style lang="sass" scoped>
html
  width: 100%
  height: 100%

body
  height: 100%
  width: 100%
  display: flex
  align-items: center
  justify-content: center

button
  position: relative
  outline: none
  text-decoration: none
  border-radius: 50px
  display: flex
  justify-content: center
  align-items: center
  cursor: pointer
  text-transform: uppercase
  height: 60px
  width: 210px
  opacity: 1
  background-color: #ffffff
  border: 1px solid rgba(22, 76, 167, 0.6)
  span
    color: rgba(22, 76, 167, 1)
    font-size: 12px
    font-weight: 500
    letter-spacing: 0.7px
  &:hover
    animation: rotate 0.7s ease-in-out both
    span
      animation: storm 0.7s ease-in-out both
      animation-delay: 0.06s

@keyframes rotate
  0%
    transform: rotate(0deg) translate3d(0, 0, 0)
  25%
    transform: rotate(3deg) translate3d(0, 0, 0)
  50%
    transform: rotate(-3deg) translate3d(0, 0, 0)
  75%
    transform: rotate(1deg) translate3d(0, 0, 0)
  100%
    transform: rotate(0deg) translate3d(0, 0, 0)

@keyframes storm
  0%
    transform: translate3d( 0, 0, 0) translateZ(0)
  25%
    transform: translate3d( 4px, 0, 0) translateZ(0)
  50%
    transform: translate3d( -3px, 0, 0) translateZ(0)
  75%
    transform: translate3d( 2px, 0, 0) translateZ(0)
  100%
    transform: translate3d( 0, 0, 0) translateZ(0)
</style>