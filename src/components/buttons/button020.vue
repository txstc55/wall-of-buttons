<template>
  <div class="relative w-full h-full flex items-center justify-center">
    <div
      class="relative container mx-auto flex flex-wrap justify-between gap-y-2 h-96 w-60 mb-8 text-xl bg-black"
    >
      <button class="w-44 h-12 bg-yellow-600 rounded-full"></button>
      <button
        class="w-12 h-12 border-4 border-yellow-300 rounded-full text-yellow-200 flex items-center justify-center"
      >
        <svg
          class="w-7 h-7 rotate-180-anim"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            stroke-linecap="square"
            stroke-linejoin="round"
            stroke-width="2"
            d="M5 10l7-7m0 0l7 7m-7-7v18"
          ></path>
        </svg>
      </button>

      <button
        class="w-28 h-12 border-4 border-purple-400 rounded-full text-purple-400 bg-anim"
      >
        <span class="white-text-anim">explore</span>
      </button>
      <button
        class="w-28 h-12 border-4 border-blue-500 rounded-full text-blue-500 bg-anim delay-1"
      >
        <span class="white-text-anim delay-1">landings</span>
      </button>

      <button class="w-12 h-12 bg-yellow-300 rounded-full"></button>
      <button class="w-44 h-12 border-4 border-green-500 rounded-full"></button>

      <button class="w-32 h-12 bg-pink-300 rounded-full text-white">
        web mags
      </button>
      <button
        class="w-12 h-12 border-4 border-blue-800 rounded-full text-blue-700 flex items-center justify-center"
      >
        <svg
          class="w-7 h-7 rotate-45-anim delay-1"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            stroke-linecap="square"
            stroke-linejoin="round"
            stroke-width="2"
            d="M19 14l-7 7m0 0l-7-7m7 7V3"
          ></path>
        </svg>
      </button>
      <button class="w-12 h-12 bg-gray-300 rounded-full"></button>

      <button class="w-12 h-12 border-4 border-gray-500 rounded-full"></button>
      <button
        class="w-44 h-12 border-4 border-yellow-600 rounded-full text-yellow-600 bg-anim delay-3"
      >
        <span class="white-text-anim delay-3">digital editorials</span>
      </button>

      <button class="w-28 h-12 bg-blue-500 rounded-full text-white">
        <svg
          class="w-full h-6"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M17 8l4 4m0 0l-4 4m4-4H3"
          ></path>
        </svg>
      </button>
      <button
        class="w-28 h-12 border-4 border-blue-700 bg-black rounded-full text-blue-700 bg-anim anim-reverse delay-3"
      >
        <span class="white-text-anim anim-reverse delay-3">readmag</span>
      </button>

      <button
        class="w-20 h-12 border-4 border-green-600 rounded-full text-green-600 bg-anim delay-2 duration-5"
      ></button>
      <button
        class="w-24 h-12 border-4 border-purple-500 rounded-full"
      ></button>
      <button
        class="w-12 h-12 border-4 border-yellow-600 text-yellow-600 rounded-full bg-anim duration-1"
      ></button>
    </div>
  </div>
</template>

<script>
// this button is from:
// https://codepen.io/lalacode/pen/jOZLaPY
export default {
  name: "button20",
};
</script>

<style lang="sass" scoped>
.rotate-180-anim
  animation: rotate180 4s linear infinite
@keyframes rotate180
  0%
    transform: rotate(0deg)
  15%
    transform: rotate(180deg)
  50%
    transform: rotate(180deg)
  65%
    transform: rotate(0deg)
  100%
    transform: rotate(0deg)

.rotate-45-anim
  transform: rotate(-45deg)
  animation: rotate45 4s linear infinite
@keyframes rotate45
  0%
    transform: rotate(-45deg)
  15%
    transform: rotate(45deg)
  50%
    transform: rotate(45deg)
  65%
    transform: rotate(-45deg)
  100%
    transform: rotate(-45deg)

.bg-anim
  animation: changebg 2s steps(2, jump-none) infinite
@keyframes changebg
  from
    background-color: #000
  to
    background-color: currentcolor

.white-text-anim
  animation: changewh 2s steps(2, jump-none) infinite
@keyframes changewh
  from
    color: currentcolor
  to
    color: #fff

.delay-1
  animation-delay: 1s
.delay-2
  animation-delay: 2s
.delay-3
  animation-delay: 2.5s

.anim-reverse
  animation-direction: reverse

.duration-5
  animation-duration: 5s
.duration-1
  animation-duration: 1s
</style>
