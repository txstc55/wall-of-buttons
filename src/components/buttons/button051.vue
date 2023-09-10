<template>
  <div class="circle_black long">
    <p>Submit</p>
  </div>
</template>

<script>
// this button is from:
// https://codepen.io/Shinobis/pen/yLNgWGM
export default {
  name: "button51",
};
</script>

<style scoped>
section.dark {
  display: flex;
  width: 50vw;
  height: 100vh;
  align-items: center;
  justify-content: space-around;
}
section.dark {
  background-color: #131419;
}
div.circle_black {
  position: relative;
  display: flex;
  width: 150px;
  height: 150px;
  border-radius: 150px;
  align-items: center;
  justify-content: center;
}
div.circle_black:before {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  display: block;
  width: 150px;
  height: 150px;
  content: " ";
  cursor: pointer;
  transition: 0.3s ease-out;
  border-radius: 150px;
  filter: blur(7px);
}
div.circle_black.long {
  width: 250px;
  height: 100px;
}
div.circle_black.long:before {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  width: 250px;
  height: 100px;
}
div.circle_black:before {
  box-shadow: 8px 8px 20px rgba(0, 0, 0, 0.5),
    -8px -8px 20px rgba(255, 255, 255, 0.2);
}
div.circle_black:hover:before {
  box-shadow: 8px 8px 20px rgba(0, 0, 0, 0.5),
    -8px -8px 20px rgba(255, 255, 255, 0.2), inset 8px 8px 20px rgba(0, 0, 0, 1),
    inset -8px -8px 20px rgba(255, 255, 255, 0.2);
}
div.circle_black:hover:before {
  transition: 0.3s ease-in;
  transform: scale(1.05);
}
div.circle_black p {
  position: relative;
  z-index: 5;
  user-select: none;
  cursor: pointer;
}
div.circle_black {
  color: white;
}
@media (max-width: 700px) {
  body {
    height: auto;
    flex-direction: column;
  }
  section.light,
  section.dark {
    width: 100vw;
    height: 100vh;
  }
}
</style>