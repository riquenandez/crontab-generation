<template>
  <div class="crontabGenerator">
    <h1>Crontab Command Generator</h1>

    <section class="buttons">
      <button v-on:click="test()">Generate Command</button>
      <button v-on:click="clear()">Clear</button>
      <input type="radio" value="Yes" />
    </section>

    <section class="test">
      <Description v-bind:parameters="parameters" />
      <Inputs v-bind:parameters="parameters" />
    </section>
    <LiveCommand v-bind:parameters="parameters" />
    <h3>{{command}}</h3>
  </div>
</template>


<script>
import LiveCommand from "./LiveCommand";
import Description from "./Description";
import Inputs from "./Inputs";

export default {
  name: "CrontabGenerator",
  components: {
    LiveCommand,

    Description,
    Inputs
  },
  data() {
    return {
      parameters: [
        { id: 1, name: "Minutes", value: null, range: "(0-59)" },
        { id: 2, name: "Hour", value: null, range: "(0-23)" },
        { id: 3, name: "Day of Month", value: null, range: "(1-31)" },
        { id: 4, name: "Month", value: null, range: "(1-12)" },
        { id: 5, name: "Day Of Week", value: null, range: "(0-7)" },
        { id: 6, name: "Linux Command", value: null, range: "Linux Command" }
      ],
      command: "Your Command: "
    };
  },
  methods: {
    test: function() {
      let inputs = this.parameters;
      inputs.forEach(element => {
        if (element.value == null) {
          element.value = "*";
          this.command += element.value;
        }
      });
    },
    clear: function() {
      this.parameters.forEach(element => {
        element.value = null;
      });
      this.command = "";
    }
  }
};
</script>

<style scoped>
.crontabGenerator {
  align-content: center;
  align-items: center;
  width: auto;
  height: auto;
  background-color: antiquewhite;
}
button {
  margin-right: 10px;
}

h3 {
  margin: 0;
}

.buttons {
  display: flex;
  padding: 10px;
}

.test {
  display: flex;
  align-items: center;
  /* justify-content: space-between; */
}
</style>