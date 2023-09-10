<template>
  <div class="container010">
    <div class="btn"><a href="#" onclick="return false;">Click Me</a></div>
  </div>
</template>

<script>
// this button is from:
// https://codepen.io/katarzynamarta/pen/rNdbbVq
export default {
  name: "button12",
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700;800;900&family=Roboto:wght@400;500;700&display=swap");

.container010 {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
.container010 .btn {
  position: relative;
  top: 0;
  left: 0;
  width: 250px;
  height: 50px;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
.container010 .btn a {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: rgba(255, 255, 255, 0.05);
  box-shadow: 0 15px 15px rgba(0, 0, 0, 0.3);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 30px;
  padding: 10px;
  letter-spacing: 1px;
  text-decoration: none;
  overflow: hidden;
  color: #fff;
  font-weight: 400px;
  z-index: 1;
  transition: 0.5s;
  backdrop-filter: blur(15px);
}
.container010 .btn:hover a {
  letter-spacing: 3px;
}
.container010 .btn a::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 50%;
  height: 100%;
  background: linear-gradient(to left, rgba(255, 255, 255, 0.15), transparent);
  transform: skewX(45deg) translate(0);
  transition: 0.5s;
  filter: blur(0px);
}
.container010 .btn:hover a::before {
  transform: skewX(45deg) translate(200px);
}
.container010 .btn::before {
  content: "";
  position: absolute;
  left: 50%;
  transform: translatex(-50%);
  bottom: -5px;
  width: 30px;
  height: 10px;
  background: #f00;
  border-radius: 10px;
  transition: 0.5s;
  transition-delay: 0.5;
}
.container010 .btn:hover::before /*lightup button*/ {
  bottom: 0;
  height: 50%;
  width: 80%;
  border-radius: 30px;
}

.container010 .btn::after {
  content: "";
  position: absolute;
  left: 50%;
  transform: translatex(-50%);
  top: -5px;
  width: 30px;
  height: 10px;
  background: #f00;
  border-radius: 10px;
  transition: 0.5s;
  transition-delay: 0.5;
}
.container010 .btn:hover::after /*lightup button*/ {
  top: 0;
  height: 50%;
  width: 80%;
  border-radius: 30px;
}
.container010 .btn:nth-child(1)::before, /*chnage 1*/
.container010 .btn:nth-child(1)::after {
  background: #ff1f71;
  box-shadow: 0 0 5px #ff1f71, 0 0 15px #ff1f71, 0 0 30px #ff1f71,
    0 0 60px #ff1f71;
}
.container010 .btn:nth-child(2)::before, /* 2*/
.container010 .btn:nth-child(2)::after {
  background: #2db2ff;
  box-shadow: 0 0 5px #2db2ff, 0 0 15px #2db2ff, 0 0 30px #2db2ff,
    0 0 60px #2db2ff;
}
.container010 .btn:nth-child(3)::before, /* 3*/
.container010 .btn:nth-child(3)::after {
  background: #1eff45;
  box-shadow: 0 0 5px #1eff45, 0 0 15px #1eff45, 0 0 30px #1eff45,
    0 0 60px #1eff45;
}
</style>
