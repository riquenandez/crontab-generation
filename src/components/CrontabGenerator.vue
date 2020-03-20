<template>
  <div class="crontabGenerator">
    <h1>Crontab Command Generator</h1>
    <input type="text" v-model="minute" placeholder="minutes: (0-59)" />
    <input type="text" v-model="hour" placeholder="hour: (0-23)" />
    <input type="text" v-model="dayOfMonth" placeholder="day of month (1-31)" />
    <input type="text" v-model="month" placeholder="month: (1-12)" />
    <input type="text" v-model="dayOfWeek" placeholder="Weekday: (0-7)" />
    <input type="text" v-model="commandToExecute" placeholder="Linux Command" />

    <LiveCommand
      :minute="minute"
      :hour="hour"
      :dayOfMonth="dayOfMonth"
      :month="month"
      :dayOfWeek="dayOfWeek"
      :commandToExecute="commandToExecute"
    />
    <button v-on:click="generateCommand()">Generate Command</button>
    <button v-on:click="clearCommand()">Clear</button>
    <h3>{{command}}</h3>
  </div>
</template>


<script>
import LiveCommand from "./LiveCommand";

export default {
  name: "CrontabGenerator",
  components: {
    LiveCommand
  },
  data() {
    return {
      minute: "",
      hour: "",
      dayOfMonth: "",
      month: "",
      dayOfWeek: "",
      commandToExecute: "",
      command: ""
    };
  },
  methods: {
    generateCommand: function() {
      this.command = `Your Command:  ${this.minute} ${this.hour} ${this.dayOfMonth} ${this.month} ${this.dayOfWeek} ${this.commandToExecute}`;
    },
    clearCommand: function() {
      this.command = "";
    }
  }
};
</script>

<style scoped>
.crontabGenerator {
  text-align: center;
  align-content: center;
  align-items: center;
  width: auto;
  height: auto;
  background-color: antiquewhite;
}
button {
  margin-right: 10px;
}
</style>