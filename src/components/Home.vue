<template>
  <div>
    <div>
      <p class="band">The {{ bandName }}</p>
    </div>
    <div>
      <button class="button" v-on:click="newBandName">New Bandname</button>
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
.band {
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  font-size: 25pt;
}
.button {
  border-width: 1px;
  color: #363636;
  cursor: pointer;
  justify-content: center;
  padding-bottom: calc(0.5em - 1px);
  padding-left: 1em;
  padding-right: 1em;
  padding-top: calc(0.5em - 1px);
  text-align: center;
  white-space: nowrap;
  background-color: #040404;
  border-color: transparent;
  color: #fff;
  border-radius: 4px;
  box-shadow: #040404;
}
</style>
