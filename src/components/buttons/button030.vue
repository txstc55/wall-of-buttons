<template>
  <button class="button-perspective" role="button">Perspective</button>
</template>

<script>
// this button is from:
// https://codepen.io/fabiocberg/pen/wvqpXqg
export default {
  name: "button30",
};
</script>

<style scoped>
/* PERPECTIVE */
.button-perspective {
  background-color: #3dd1e7;
  border: 0 solid #e5e7eb;
  box-sizing: border-box;
  color: #000000;
  display: flex;
  font-family: ui-sans-serif, system-ui, -apple-system, system-ui, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif,
    "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  font-size: 1rem;
  font-weight: 700;
  justify-content: center;
  line-height: 1.75rem;
  padding: 0.75rem 1.65rem;
  position: relative;
  text-align: center;
  text-decoration: none #000000 solid;
  text-decoration-thickness: auto;
  width: 100%;
  max-width: 460px;
  position: relative;
  cursor: pointer;
  transform: rotate(-2deg);
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.button-perspective:focus {
  outline: 0;
}

.button-perspective:after {
  content: "";
  position: absolute;
  border: 1px solid #000000;
  bottom: 4px;
  left: 4px;
  width: calc(100% - 1px);
  height: calc(100% - 1px);
}

.button-perspective:hover:after {
  bottom: 2px;
  left: 2px;
}

@media (min-width: 768px) {
  .button-perspective {
    padding: 0.75rem 3rem;
    font-size: 1.25rem;
  }
}
</style>
