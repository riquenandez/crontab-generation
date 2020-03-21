/*
Crontab Generator Vue component.

Consists of 3 major sections:
  First section hosts the method activation buttons.
  Second section hosts the generation and clear command buttons.
  Third sections consists of Inputs and LiveCommand components.

This component hosts the input parameters and command data objects, 
  as well as the crontab generation methods

If you wish you to add a new crontab generation function, you can include it under methods.

*/

<template>
  <div class="crontabGenerator">
    <h1>Crontab Command Generator</h1>
    <section class="buttons">
      <button v-on:click="everyTenMin()">Every 10 minutes</button>
      <button v-on:click="everyHour()">Every Hour</button>
      <button v-on:click="businessHours()">Business Hours</button>
      <button v-on:click="daily()">Run daily</button>
      <button v-on:click="mondayToFriday()">Monday-Friday</button>
      <button v-on:click="quarterly()">Every Quarter</button>
    </section>
    <section class="buttons">
      <button v-on:click="generateCommand()">Generate Command</button>
      <button v-on:click="clearCommand()">Clear</button>
    </section>
    <section class="inputInterface">
      <Inputs v-bind:parameters="parameters" />
      <LiveCommand v-bind:parameters="parameters" />
    </section>
    <p>Note: Empty fields will default to '*'</p>
    <h3>Your Command: {{command}}</h3>
  </div>
</template>


<script>
//import components
import LiveCommand from "./LiveCommand";
import Inputs from "./Inputs";

export default {
  name: "CrontabGenerator",
  components: {
    LiveCommand,
    Inputs
  },
  data() {
    return {
      parameters: [
        { id: 1, name: "Minutes", value: null, range: "(0-59)" },
        { id: 2, name: "Hour", value: null, range: "(0-23)" },
        { id: 3, name: "Day of Month", value: null, range: "(1-31)" },
        { id: 4, name: "Month", value: null, range: "(1-12)" },
        { id: 5, name: "Day of Week", value: null, range: "(0-7)" },
        {
          id: 6,
          name: "Command To Execute",
          value: null,
          range: "Linux Command"
        }
      ],
      command: ""
    };
  },
  methods: {
    generateCommand: function() {
      const inputs = this.parameters;
      //clears commmand before generating new command
      this.command = "";

      //command generating loop
      inputs.forEach(element => {
        //check to see if element values are empty
        if (element.value == null) {
          //filter out Linux Command field
          if (element.name !== "Command To Execute") {
            //set element value to '*' if empty
            element.value = "*";
            this.command += element.value + " ";
          } else {
            //set Linux Command to example str if empty
            element.value = "command_to_execute";
            this.command += element.value + " ";
          }
        } else {
          //add element values to command
          this.command += element.value + " ";
        }
      });
    },
    clearCommand: function() {
      //clear input and command values
      this.parameters.forEach(element => {
        element.value = null;
      });
      this.command = "";
    },
    everyTenMin: function() {
      //generates every 10 minutes values
      let minutes = this.parameters[0];
      minutes.value = "*/10";
    },
    daily: function() {
      //sets Day of month, month, and day of week fields to '*'
      this.parameters.forEach(element => {
        if (element.id == "3" || element.id == "4" || element.id == "5") {
          element.value = "*";
        }
      });
    },
    mondayToFriday: function() {
      //sets day of week to monday-friday value
      let weekDay = this.parameters[4];
      weekDay.value = "1-5";
    },
    businessHours: function() {
      //set hour value to 9:00am-5:00pm
      const hour = this.parameters[1];
      hour.value = "9-17";
    },
    quarterly: function() {
      //quarterly crontab, first day of every 3rd month
      this.parameters.forEach(element => {
        if (element.id == "5") {
          element.value = "*";
        } else if (element.id == "4") {
          element.value = "*/3";
        } else if (element.id == "3") {
          element.value = "1";
        } else if (element.id == "1" || element.id == "2") {
          element.value = "0";
        }
      });
    },
    everyHour: function() {
      this.parameters[0].value = "0";
    }
  }
};
</script>

<style scoped>
.crontabGenerator {
  background-color: white;
  border-radius: 25px;
}
h1 {
  text-align: center;
  padding-top: 10px;
}
button {
  margin-right: 10px;
}

h3,
p {
  padding-bottom: 20px;
  padding-left: 20px;
  margin: 0;
}

.buttons {
  display: flex;
  padding: 10px;
  justify-content: center;
}

.inputInterface {
  display: flex;
  align-items: center;
  padding: 10px;
}
</style>