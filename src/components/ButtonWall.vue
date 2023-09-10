<template>
  <div class="w-auto h-full grid">
    <div
      class="flex flex-col items-center w-auto rounded-md shadow-xl ease-in-out duration-300 scale-90 hover:scale-100 grid-item bg-slate-500/80 backdrop-blur-sm hover:bg-slate-900/80 py-5 px-10 border-2 border-slate-600/60 shadow-slate-700 hover:shadow-2xl m-4"
      v-for="comp in loadedComponents"
      :key="comp.name"
    >
      <div
        class="whitespace-nowrap overflow-hidden text-ellipsis text-center font-mono font-semibold text-gray-100 text-2xl"
      >
        Button {{ pad(comp.componentID) }} has been<br />
        clicked
        <span class="text-white font-extrabold text-3xl">3</span> times
      </div>
      <div
        class="content-center items-center justify-center text-center my-32 flex-shrink-0"
      >
        <component
          :is="comp.component"
          @click="console.log('Button ' + comp.componentID + ' clicked')"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Packery from "packery";

const componentFiles = require.context("./buttons", false, /\.vue$/);

// randomize an array
function shuffle(array) {
  let currentIndex = array.length,
    randomIndex;

  // While there remain elements to shuffle.
  while (currentIndex > 0) {
    // Pick a remaining element.
    randomIndex = Math.floor(Math.random() * currentIndex);
    currentIndex--;

    // And swap it with the current element.
    [array[currentIndex], array[randomIndex]] = [
      array[randomIndex],
      array[currentIndex],
    ];
  }

  return array;
}

var componentID = 0;
const components = componentFiles.keys().map((filename) => {
  const componentName = filename.replace(/^\.\/(.*)\.\w+$/, "$1");
  return {
    name: componentName,
    component: componentFiles(filename).default,
    componentID: componentID++,
  };
});

// shuffle(components);

export default {
  name: "ButtonWall",
  data() {
    return {
      loadedComponents: components,
    };
  },
  methods: {
    pad(n, f = 4) {
      var s = "0".repeat(f) + n;
      return s.substr(s.length - f);
    },
  },
  mounted() {
    var grid = document.querySelector(".grid");
    var pckry = new Packery(grid, {
      // options...
      itemSelector: ".grid-item",
    });
    pckry.layout();
    window.addEventListener("resize", () => {
      // vanilla JS
      grid = document.querySelector(".grid");
      // initialize with element
      pckry = new Packery(grid, {
        // options...
        itemSelector: ".grid-item",
      });
      pckry.layout();
    });
  },
  created() {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
