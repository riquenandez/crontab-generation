/*
App Vue component

This component renders the CrontabGenerator component.

*/

<template>
  <div id="app">
    <CrontabGenerator />
  </div>
</template>

<script>
//import ContrabGenerator component
import CrontabGenerator from "./components/CrontabGenerator";
export default {
  name: "App",
  components: {
    CrontabGenerator
  }
};
</script>

<style>
html,
body {
  background-color: rgb(235, 235, 235);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: rgb(235, 235, 235);
  color: #2c3e50;
}
</style>
