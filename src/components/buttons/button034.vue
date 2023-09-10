<template>
  <a class="btn v1">Learn More</a>
</template>

<script>
// this button is from:
// https://codepen.io/carsonf92/pen/ExmNoRp
export default {
  name: "button34",
};
</script>

<style lang="scss" scoped>
$gold: #c4ae59;
$navy: #1d2b48;

html {
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  font-size: 62.5%; // 1rem = 10px
}

body {
  align-items: center;
  background-color: #5b7b98;
  display: flex;
  flex-direction: column;
  justify-content: center;
  min-height: 100vh;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

hr {
  border: none;
  border-top: 2px solid #3b5b78;
  margin: 20px 0;
  width: 80px;
}

.btn {
  color: white;
  cursor: pointer;
  font: bold 2.4rem "Barlow Condensed";
  letter-spacing: 0.1rem;
  overflow: hidden;
  padding: 10px 100px;
  position: relative;
  text-transform: uppercase;
  z-index: 1;
}

.btn.v1 {
  background-color: $navy;
  transition: background-color 0.4s ease;

  &::before,
  &::after {
    background: url("data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4KPCEtLSBHZW5lcmF0b3I6IEFkb2JlIElsbHVzdHJhdG9yIDI1LjMuMSwgU1ZHIEV4cG9ydCBQbHVnLUluIC4gU1ZHIFZlcnNpb246IDYuMDAgQnVpbGQgMCkgIC0tPgo8c3ZnIHZlcnNpb249IjEuMSIgaWQ9IkxheWVyXzEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiIHg9IjBweCIgeT0iMHB4IgoJIHZpZXdCb3g9IjAgMCA2MCAxMS40IiBzdHlsZT0iZW5hYmxlLWJhY2tncm91bmQ6bmV3IDAgMCA2MCAxMS40OyIgeG1sOnNwYWNlPSJwcmVzZXJ2ZSI+CjxzdHlsZSB0eXBlPSJ0ZXh0L2NzcyI+Cgkuc3Qwe2ZpbGw6I0M0QUU1OTt9Cjwvc3R5bGU+CjxwYXRoIGlkPSJQYXRoXzE2NzciIGNsYXNzPSJzdDAiIGQ9Ik01OC43LDUuMkw0NS41LDBsMi4zLDUuMUgxOGwtNC4yLTQuMkgwbDQuOSw0LjlMMCwxMC41aDEzLjhMMTgsNi4zaDI5LjhsLTIuMyw1LjFsMTMuMi01LjIKCUw2MCw1LjdMNTguNyw1LjJ6IE01NC42LDYuNGwtNi43LDIuNmwxLjItMi42SDU0LjZ6IE0zLjEsOS4zbDMtM2gxMC4ybC0zLDNIMy4xeiIvPgo8L3N2Zz4K")
      center/contain no-repeat;
    content: "";
    display: block;
    height: 12px;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 60px;
    z-index: 1;
  }

  &::before {
    left: 20px;
    transform: translate(calc(-100% - 20px), -50%);
    transition: transform 0.2s ease;
  }

  &::after {
    right: 20px;
    transition: transform 0.2s ease 0.1s;
  }

  &:hover {
    background-color: darken($navy, 5%);

    &::before {
      transform: translate(0, -50%);
      transition: transform 0.2s ease 0.1s;
    }

    &::after {
      transform: translate(calc(100% + 20px), -50%);
      transition: transform 0.2s ease;
    }
  }
}

.btn.v2 {
  padding: 10px 100px 10px 20px;
  transition: color 0.2s ease;

  &::before {
    background: linear-gradient(90deg, darken($navy, 5%) 50%, $navy 50%);
    content: "";
    height: 100%;
    right: 0;
    position: absolute;
    top: 0;
    transition: transform 0.2s ease;
    width: 200%;
    z-index: -1;
  }

  &::after {
    background: url("data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4KPCEtLSBHZW5lcmF0b3I6IEFkb2JlIElsbHVzdHJhdG9yIDI1LjMuMSwgU1ZHIEV4cG9ydCBQbHVnLUluIC4gU1ZHIFZlcnNpb246IDYuMDAgQnVpbGQgMCkgIC0tPgo8c3ZnIHZlcnNpb249IjEuMSIgaWQ9IkxheWVyXzEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiIHg9IjBweCIgeT0iMHB4IgoJIHZpZXdCb3g9IjAgMCA2MCAxMS40IiBzdHlsZT0iZW5hYmxlLWJhY2tncm91bmQ6bmV3IDAgMCA2MCAxMS40OyIgeG1sOnNwYWNlPSJwcmVzZXJ2ZSI+CjxzdHlsZSB0eXBlPSJ0ZXh0L2NzcyI+Cgkuc3Qwe2ZpbGw6I0M0QUU1OTt9Cjwvc3R5bGU+CjxwYXRoIGlkPSJQYXRoXzE2NzciIGNsYXNzPSJzdDAiIGQ9Ik01OC43LDUuMkw0NS41LDBsMi4zLDUuMUgxOGwtNC4yLTQuMkgwbDQuOSw0LjlMMCwxMC41aDEzLjhMMTgsNi4zaDI5LjhsLTIuMyw1LjFsMTMuMi01LjIKCUw2MCw1LjdMNTguNyw1LjJ6IE01NC42LDYuNGwtNi43LDIuNmwxLjItMi42SDU0LjZ6IE0zLjEsOS4zbDMtM2gxMC4ybC0zLDNIMy4xeiIvPgo8L3N2Zz4K")
      center/contain no-repeat;
    content: "";
    display: block;
    height: 12px;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 60px;
    z-index: 1;
  }

  &::after {
    right: 20px;
    transition: transform 0.2s ease;
  }

  &:hover {
    color: lighten($gold, 10%);

    &::before {
      transform: translateX(50%);
    }

    &::after {
      transform: translate(10px, -50%);
    }
  }
}
</style>
