<template>
  <div>
    <div>
      <p>The {{ bandName }}</p>
    </div>
    <div>
      <button v-on:click="newBandName">New Bandname</button>
    </div>
  </div>
</template>

<script>
import { words } from "../assets/words.js";

String.prototype.capitalize = function () {
  return this.charAt(0).toUpperCase() + this.slice(1);
};
const sample = (arr) => {
  return arr[Math.floor(Math.random() * arr.length)];
};
export default {
  data: () => {
    return {
      bandName: "Placeholders",
      bandNames: [],
    };
  },
  created() {
    this.bandNames = words;
  },
  methods: {
    newBandName: function () {
      this.bandName = sample(this.bandNames).capitalize();
    },
  },
};
</script>

<style>
</style>
