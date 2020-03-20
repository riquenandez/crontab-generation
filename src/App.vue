<template>
  <div id="app">
    <h1>Crontab Command Generator</h1>

    <CrontabGui />
  </div>
</template>

<script>
import CrontabGui from "./components/CrontabGui";
export default {
  name: "App",
  components: {
    CrontabGui
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
