<template>
  <div>
    <input type="text" v-model="minute" />
    <input type="text" v-model="hour" />
    <input type="text" v-model="dayOfMonth" />
    <input type="text" v-model="month" />
    <input type="text" v-model="dayOfWeek" />
    <input type="text" v-model="commandToExecute" />

    <Command
      :minute="minute"
      :hour="hour"
      :dayOfMonth="dayOfMonth"
      :month="month"
      :dayOfWeek="dayOfWeek"
      :commandToExecute="commandToExecute"
    />
    <button v-on:click="generateCommand()">Generate Command</button>
    {{command}}
  </div>
</template>


<script>
import Command from "./Command";
export default {
  name: "ContrabGui",
  components: {
    Command
  },
  data() {
    return {
      minute: "*",
      hour: "*",
      dayOfMonth: "*",
      month: "*",
      dayOfWeek: "*",
      commandToExecute: "command_to_execute",
      command: ""
    };
  },
  methods: {
    generateCommand: function() {
      this.command = `Your Command:  ${this.minute} ${this.hour} ${this.dayOfMonth} ${this.month} ${this.dayOfWeek} ${this.commandToExecute}`;
    }
  }
};
</script>

<style>
</style>