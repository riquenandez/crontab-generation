<template>
  <div class="crontab">
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
  name: "Command",
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
.crontab {
  display: flex;
  width: 100%;
}
p {
  display: flex;
  width: auto;
  padding: 5px;
}
</style>