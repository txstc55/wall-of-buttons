<template>
  <button>
    Click me
    <svg
      width="79"
      height="46"
      viewBox="0 0 79 46"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <g filter="url(#filter0_f_618_1123)">
        <path
          d="M42.9 2H76.5L34.5 44H2L42.9 2Z"
          fill="url(#paint0_linear_618_1123)"
        />
      </g>
      <defs>
        <filter
          id="filter0_f_618_1123"
          x="0"
          y="0"
          width="78.5"
          height="46"
          filterUnits="userSpaceOnUse"
          color-interpolation-filters="sRGB"
        >
          <feFlood flood-opacity="0" result="BackgroundImageFix" />
          <feBlend
            mode="normal"
            in="SourceGraphic"
            in2="BackgroundImageFix"
            result="shape"
          />
          <feGaussianBlur
            stdDeviation="1"
            result="effect1_foregroundBlur_618_1123"
          />
        </filter>
        <linearGradient
          id="paint0_linear_618_1123"
          x1="76.5"
          y1="2.00002"
          x2="34.5"
          y2="44"
          gradientUnits="userSpaceOnUse"
        >
          <stop stop-color="white" stop-opacity="0.6" />
          <stop offset="1" stop-color="white" stop-opacity="0.05" />
        </linearGradient>
      </defs>
    </svg>
  </button>
</template>

<script>
// this button is from:
// https://codepen.io/loganliffick/pen/WNdZQZQ
export default {
  name: "button22",
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap");

body {
  background: #170f1e;
  display: grid;
  height: 100vh;
  place-items: center;
  -webkit-font-smoothing: antialiased;
  width: 100vw;
}

button {
  animation: 1.5s ease infinite alternate running shimmer;
  background: linear-gradient(90deg, #ffe27d 0%, #64e3ff 30%, #9192ff 85%);
  background-size: 200% 100%;
  border: none;
  border-radius: 6px;
  box-shadow: -2px -2px 10px rgba(255, 227, 126, 0.5),
    2px 2px 10px rgba(144, 148, 255, 0.5);
  color: #170f1e;
  cursor: pointer;
  font-family: "Inter", sans-serif;
  font-size: 16px;
  font-weight: 670;
  line-height: 24px;
  overflow: hidden;
  padding: 12px 24px;
  position: relative;
  text-decoration: none;
  transition: 0.2s;

  svg {
    left: -20px;
    opacity: 0.5;
    position: absolute;
    top: -2px;
    transition: 0.5s cubic-bezier(0.5, -0.5, 0.5, 1.5);
  }

  &:hover svg {
    opacity: 0.8;
    transform: translateX(50px) scale(1.5);
  }

  &:hover {
    transform: rotate(-3deg);
  }

  &:active {
    transform: scale(0.95) rotate(-3deg);
  }
}

@keyframes shimmer {
  to {
    background-size: 100% 100%;
    box-shadow: -2px -2px 6px rgba(255, 227, 126, 0.5),
      2px 2px 6px rgba(144, 148, 255, 0.5);
  }
}
</style>
