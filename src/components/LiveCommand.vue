/*
LiveCommand Vue component.

This component displays a live preview of the user input.
It receives the input data from its parent component.

*/

<template>
  <div class="preview">
    <h3>Preview</h3>
    <section>
      <p>
        Minutes: {{parameters[0].value}}
        <br />
        Hour: {{parameters[1].value}}
        <br />
        Day Of Month: {{parameters[2].value}}
        <br />
        Month: {{parameters[3].value}}
        <br />
        Day Of Week: {{parameters[4].value}}
        <br />
        Command To Execute: {{parameters[5].value}}
      </p>
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
.preview {
  padding: 10px;
}

h3 {
  margin: 0;
}
p {
  margin: 0;
}
</style>