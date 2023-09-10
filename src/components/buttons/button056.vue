<template>
  <a href="#" onclick="return false;">
    <button class="button">Button</button>
    <div class="drip-1"></div>
    <div class="drip-2"></div>
    <div class="drip-3"></div>
  </a>
</template>

<script>
// this button is from:
// https://codepen.io/JasonCodemakers/pen/zPZzmz
export default {
  name: "button56",
};
</script>

<style scoped>
.container {
  position: relative;
  width: 400px;
  height: 400px;
  background: white;
  margin: auto;
  padding-top: 300px;
  padding-left: 120px;
}

.button {
  color: #fff;
  font-weight: normal;
  font-size: 22px;
  background: #630fe8;
  border-radius: 50px;
  padding: 30px 90px;
  border: none;
  transition: 0.5s ease;
  box-shadow: 0 15px 60px -5px rgba(0, 0, 0, 0.5);
}

.button:hover {
  box-shadow: none;
  cursor: pointer;
}

.button:hover + .drip-1 {
  height: 50px;
}

.button:hover ~ .drip-2 {
  height: 90px;
}

.button:hover ~ .drip-3 {
  height: 30px;
}

.drip-1 {
  position: absolute;
  width: 19px;
  height: 0px;
  border-radius: 0 0 21px 21px;
  background: #efd5e7;
  margin: 0px 158px;
  transition: height 0.9s ease;
}

.drip-2 {
  position: absolute;
  width: 19px;
  height: 0px;
  border-radius: 0 0 21px 21px;
  background: #efd5e7;
  margin: 0px 140px;
  transition: height 1.5s ease;
}

.drip-3 {
  position: absolute;
  width: 19px;
  height: 0px;
  border-radius: 0 0 21px 21px;
  background: #efd5e7;
  margin: 0px 60px;
  transition: height 0.7s ease;
}
</style>