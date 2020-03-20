<template>
  <div>
    <p>{{name}}</p>
    <p>{{range}}</p>
  </div>
</template>

<script>
export default {
  name: "InputItem",
  props: ["name", "range", "parameter"]
};
</script>

<style>
</style>