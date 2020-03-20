<template>
  <div id="app">
    <h1>Contrab Command Generator</h1>

    <ContrabGui />
  </div>
</template>

<script>
import ContrabGui from "./components/ContrabGui";
export default {
  name: "App",
  components: {
    ContrabGui
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
