<template>
  <div class="liveCommand">
    <p>{{minute}}</p>
    <p>{{hour}}</p>
    <p>{{dayOfMonth}}</p>
    <p>{{month}}</p>
    <p>{{dayOfWeek}}</p>
    <p>{{commandToExecute}}</p>
  </div>
</template>

<script>
export default {
  name: "LiveCommand",
  props: [
    "minute",
    "hour",
    "dayOfMonth",
    "month",
    "dayOfWeek",
    "commandToExecute"
  ]
};
</script>

<style scoped>
.liveCommand {
  display: flex;
  text-align: center;
}
p {
  padding: 5px;
}
</style>