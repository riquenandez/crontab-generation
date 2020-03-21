/*
Inputs Vue component. 

This component renders input elements based on the 
number of input parameters passed down by parent component

*/
<template>
  <section class="inputs">
    <h3>Inputs</h3>
    <div v-for="parameter in parameters" :key="parameter.id">
      <input type="text" v-model="parameter.value" :placeholder="parameter.range" />
    </div>
  </section>
</template>

<script>
export default {
  name: "Inputs",
  props: ["parameters"]
};
</script>

<style scoped>
h3 {
  margin: 0;
}
.inputs {
  padding-left: 10px;
}
</style>