<template>
  <div id="app">
    <CrontabGenerator />
  </div>
</template>

<script>
import CrontabGenerator from "./components/CrontabGenerator";
export default {
  name: "App",
  components: {
    CrontabGenerator
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
