<template>
  <div class="liveCommand">
    <h3>Preview:</h3>
    <section class="preview">
      <p>{{parameters[0].value}}</p>
    </section>
  </div>
</template>

<script>
export default {
  name: "LiveCommand",
  props: ["parameters"]
};
</script>

<style scoped>
.liveCommand {
  display: flex;
  margin: 0;
  padding: 0;
  flex-direction: column;
}

.preview {
  height: 30px;
}
h3 {
  margin: 0;
}
p {
  padding: 5px;
  margin: 0;
}
</style>