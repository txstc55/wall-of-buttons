<template>
  <button>Explore the stack</button>
</template>

<script>
// this button is from:
// https://codepen.io/felipebernardes/pen/oWQOKr
export default {
  name: "button58",
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css?family=Barrio|Montserrat:700");
$green: #00d166;

body {
  font-family: "Montserrat", sans-serif;
  display: flex;
  height: 100vh;
  width: 100vw;
  background: #111;
}

button {
  margin: auto;
  padding: 1rem;
  text-transform: uppercase;
  color: #fafafa;
  background-color: $green;
  border: none;
  border-radius: 3px;
  box-shadow: 1px 1px 10px rgba(50, 50, 50, 0.4);
  transition: 0.3s all ease;
  letter-spacing: 0.1rem;
  font-size: 0.85rem;
  position: relative;
  top: 0;
  right: 0;
  padding-left: 2.5rem;

  &:after,
  &:before {
    position: absolute;
    font-family: "Barrio", sans-serif;
    font-weight: bold;
    font-size: 1rem;
    color: darken($green, 20%);
    transition: 0.3s all ease;
  }

  &:before {
    content: "_";
    position: absolute;
    left: 1.4rem;
    top: 0.9rem;
  }

  &:after {
    content: ">";
    position: absolute;
    left: 0.8rem;
    top: 1rem;
  }

  &:hover {
    box-shadow: 1px 1px 20px rgba(150, 150, 150, 0.2);
    top: -0.1rem;
    right: -0.1rem;
    cursor: pointer;

    &:before {
      content: "_";
      position: absolute;
      left: 0.8rem;
      top: 0.7rem;
      transform: translateY(-1px);
    }

    &:after {
      content: ">";
      position: absolute;
      left: 1.1rem;
      top: 1rem;
    }
  }
}
</style>