<template>
  <button type="button" class="btn btn--purple">
    <span class="btn__txt">Purple button</span>
    <i class="btn__bg" aria-hidden="true"></i>
    <i class="btn__bg" aria-hidden="true"></i>
    <i class="btn__bg" aria-hidden="true"></i>
    <i class="btn__bg" aria-hidden="true"></i>
  </button>
</template>

<script>
// this button is from:
// https://codepen.io/jh3y/pen/oNqdmbW
export default {
  name: "button17",
};
</script>

<style lang="scss" scoped>
// 90 = 360/no of layers (4 in my case)
$hueStep: 90;
$delayStep: 0.115s;

html,
body {
  height: 100%;
}

body {
  display: grid;
  place-content: center;
}

.btn {
  background: hsl(var(--hue), 98%, 80%);
  border: none;
  border-radius: 7px;
  cursor: pointer;
  color: black;
  font: 600 1.05rem/1 "Nunito", sans-serif;
  letter-spacing: 0.05em;
  overflow: hidden;
  padding: 1.15em 3.5em;
  min-height: 3.3em;
  position: relative;
  text-transform: lowercase;

  &--yellow {
    --hue: 46;
  }

  &--green {
    --hue: 163;
  }

  &--purple {
    --hue: 244;
  }

  &--red {
    --hue: 0;
  }

  &--blue {
    --hue: 210;
  }

  &:active,
  &:focus {
    outline: 3px solid hsl(calc(var(--hue) + #{$hueStep}), 98%, 80%);
  }

  & + & {
    margin-top: 2.5em;
  }

  &__txt {
    position: relative;
    z-index: 2;
  }

  &__bg {
    background: hsl(var(--hueBg), 98%, 80%);
    border-radius: 50%;
    display: block;
    height: 0;
    left: 50%;
    margin: -50% 0 0 -50%;
    padding-top: 100%;
    position: absolute;
    top: 50%;
    width: 100%;
    transform: scale(0);
    transform-origin: 50% 50%;
    transition: transform 0.175s cubic-bezier(0.5, 1, 0.89, 1);
    z-index: 1;

    @for $i from 1 through 4 {
      &:nth-of-type(#{$i}) {
        --hueBg: calc(var(--hue) - #{$i * $hueStep});
        transition-delay: $delayStep / 2 * (4 - $i);
      }
    }

    .btn:hover &,
    .btn:focus &,
    .btn:active & {
      transform: scale(1.5);
      transition: transform 0.35s cubic-bezier(0.11, 0, 0.5, 0);

      @for $i from 1 through 4 {
        &:nth-of-type(#{$i}) {
          transition-delay: $delayStep * $i;
        }
      }
    }
  }
}
</style>
