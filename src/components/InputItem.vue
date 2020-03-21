<template>
  <div class="itemContainer">
    <input class="input" type="text" v-model="parameter.value" :placeholder="parameter.range" />
  </div>
</template>

<script>
export default {
  name: "InputItem",
  props: ["parameter"]
};
</script>

<style scoped>
.itemContainer {
  width: auto;
}
</style>