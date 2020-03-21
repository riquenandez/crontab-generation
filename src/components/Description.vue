<template>
  <section>
    <div v-for="parameter in parameters" :key="parameter.id">{{parameter.name}}</div>
  </section>
</template>

<script>
export default {
  name: "Description",
  props: ["parameters"]
};
</script>

<style scoped>
section {
  width: auto;
  background-color: white;
}
</style>