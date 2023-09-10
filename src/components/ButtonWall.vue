<template>
  <div class="w-auto h-full grid">
    <div
      class="flex flex-col items-center w-auto rounded-md ease-in-out duration-300 scale-95 hover:scale-100 grid-item bg-slate-50/0 hover:bg-slate-50/10 py-5 px-10 border-slate-600/60 shadow-slate-700 hover:shadow-sm m-4 text-white/0 hover:text-white"
      v-for="comp in loadedComponents"
      :key="comp.name"
    >
      <div
        class="whitespace-nowrap overflow-hidden text-ellipsis text-center font-mono text-2xl select-none mb-8"
      >
        Button {{ pad(comp.componentID) }} has been<br />
        clicked
        <span class="font-extrabold text-2xl">{{
          allButtonRecords.length > comp.componentID
            ? allButtonRecords[comp.componentID].clicked
            : 0
        }}</span>
        times
      </div>
      <div
        class="content-center items-center justify-center text-center mb-3 flex-shrink-0 mt-2 select-none"
      >
        <component
          :is="comp.component"
          @click="updateButtonClick(comp.componentID)"
        />
      </div>
    </div>
  </div>
  <div
    class="bg-black min-w-fit w-1/3 h-64 top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 text-center select-none fixed rounded-sm py-10 border-2 font-mono border-white"
    v-if="showError"
  >
    <div class="h-24 overflow-scroll text-white text-2xl font-semibold mx-3">
      {{ error_message }}
    </div>

    <button
      class="bottom-0 absolute -translate-x-1/2 px-3 py-1 border-2 border-white rounded-sm text-xl hover:scale-105 ease-in-out duration-300 mb-4 text-white"
      @click="showError = false"
    >
      OK
    </button>
  </div>
  <button
    class="fixed bottom-2 right-2 shadow-sm w-14 h-14 font-mono text-lg rounded-full border-4 border-black bg-white hover:scale-105 ease-in-out duration-300 font-bold underline hover:text-2xl"
    @click="showInfo = true"
  >
    i
  </button>
  <div
    :class="
      'fixed bg-white w-1/3 min-w-fit h-96 text-center select-none rounded-sm backdrop-blur-xl py-4 border-4 border-black font-mono ease-in-out duration-1000 ' +
      (showInfo
        ? 'scale-100 top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 opacity-100'
        : 'scale-0 left-full top-full opacity-0 -translate-x-0 -translate-y-0')
    "
  >
    <div class="text-black text-2xl mx-4 font-semibold">
      THERE ARE JUST TOO MANY GOD DAMN BUTTON STYLES!
    </div>
    <div class="h-56 overflow-scroll px-3 py-2 text-left leading-10">
      This is just a wall of buttons I collected from the internet for no
      specific reason<br />
      You can click on your favourite button style on this wall, let others
      see!<br />
      <div class="underline font-semibold">
        Disclaimer: I did not make any of those buttons, I just copy and pasted
        them
      </div>
      If you like any of the button styles, you can find them here: <br />
      where I put the original link in the file<br />
      If you want to add any of your button styles, you can simply send a pull
      request at the github repo
    </div>

    <button
      class="bottom-2 absolute -translate-x-1/2 px-5 py-2 border-2 border-white rounded-sm text-2xl hover:border-4 hover:scale-105 ease-in-out duration-300"
      @click="showInfo = false"
    >
      OK
    </button>
  </div>
</template>

<script>
import Packery from "packery";
import PocketBase from "pocketbase";
import { markRaw } from "vue";

// get all buttons
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
    component: markRaw(componentFiles(filename).default),
    componentID: componentID++,
  };
});

// shuffle the buttons
// shuffle(components);

export default {
  name: "ButtonWall",
  data() {
    return {
      loadedComponents: components,
      allButtonRecords: [],
      showError: false,
      showInfo: false,
      error_message: "What error? No error!",
      pb: null,
    };
  },
  methods: {
    pad(n, f = 4) {
      var s = "0".repeat(f) + n;
      return s.substr(s.length - f);
    },
    async updateButtonClick(id) {
      if (this.showError) return;
      if (id >= this.allButtonRecords.length) {
        this.showError = true;
        this.error_message = "This button's info is not in the database yet!";
        return;
      }
      try {
        // first we get the actual id
        var buttonID = this.allButtonRecords[id].id;
        const data = {
          "clicked+": 1,
        };
        // we also just add one regardless
        this.allButtonRecords[id].clicked++;
        // update the record regardless
        await this.pb.collection("buttons").update(buttonID, data);
      } catch (e) {
        this.showError = true;
        this.error_message = "You are clicking too fast!";
        console.log(e);
      }
    },
  },
  async mounted() {
    try {
      this.pb = new PocketBase("https://buttons.pockethost.io");
    } catch (e) {
      this.showError = true;
      this.error_message = "Failed to connect to database";
    }
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
    // now we get all the records
    try {
      this.allButtonRecords = await this.pb.collection("buttons").getFullList({
        sort: "buttonID",
      });
    } catch (e) {
      this.showError = true;
      this.error_message =
        "Failed to get button records! Please check internet connection";
    }
    // Subscribe to changes in any buttons record
    let me = this;

    try {
      this.pb.collection("buttons").subscribe("*", function (e) {
        me.testValue++;
        if (e.action == "update") {
          me.allButtonRecords[e.record.buttonID] = e.record;
        }
      });
    } catch (e) {
      this.showError = true;
      this.error_message =
        "Failed to subscribe to button records! Please check internet connection";
      console.log(e);
    }
  },
  created() {},
  destroyed() {
    this.pb.collection("buttons").unsubscribe(); // remove all subscriptions in the collection
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
