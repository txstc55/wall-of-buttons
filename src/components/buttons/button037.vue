<template>
  <div class="center">
    <a href="#" onclick="return false;"
      ><button type="submit" class="btn">Click me</button>
    </a>
  </div>
</template>

<script>
// this button is from:
// https://codepen.io/chloe47632/pen/gOgxXGR
export default {
  name: "button37",
};
</script>

<style scoped>
body,
html {
  height: 100%;
  display: grid;
  background: #cfe0e8;
}

button {
  margin: auto;
  border-radius: 20px;
  background-color: #667292;
  box-shadow: 10px 15px 40px #36486b;
  width: 300px;
  height: 100px;
  font-size: 50px;
  font-family: cambria;
  color: #bccad6;
  border: none;
}

button:hover {
  border: none;
  background-color: #8d9db6;
  opacity: 1;
  color: #36486b;
}

.center {
  margin-left: auto;
  margin-right: auto;
  margin-top: auto;
  margin-bottom: auto;
  position: ;
}

.btn:hover {
  transition: 0.5s ease-in-out;
  background: #8d9db6;
}

button {
  --color1: #36486b;
  --color2: #bccad6;
  font-family: cambria;
  text-align: center;
  font-size: 46px;
  background: repeating-linear-gradient(
    45deg,
    var(--color1),
    var(--color1) 30px,
    var(--color2) 30px,
    var(--color2) 60px
  );
  background-clip: text;
  color: transparent;
  -webkit-background-clip: text;
  animation: 40s linear 0s infinite move;
}

@keyframes move {
  from {
    background-position: 0px;
  }

  to {
    background-position: 1000px;
  }
}
</style>
