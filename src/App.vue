<script setup>
import BodyMassIndexForm from './components/BodyMassIndexForm.vue'


import { ref } from 'vue' // added this 

// creating some reactive statements
const wryAnswer1 = ref('Height in inches')
const wryAnswer2 = ref('Weight in pounds')

// this wil store the user's answer once they made a choice

const userSelection = ref('')

function updateUserSelection(userChoice) {
  userSelection.value = `Thanks! You chose ${userChoice}`
}
// this may go with how to calculate the answers
// this goes with the function choiceMade on BodyMassIndexForm.vue

</script>

<template>

  <div id="app-component">

  <h1 id="BMIC">Body Mass Index Calculator</h1>

  <BodyMassIndexForm 
    v-bind:answer1="wryAnswer1"
    v-bind:answer2="wryAnswer2"
    v-on:stats-entered="updateUserSelection"
    ></BodyMassIndexForm>
  <!-- you can do multiple v-bind statements -->
  <!-- this will send data to the props -->

   <p> {{ userSelection }} </p>  
</div>

</template>

<style scoped>

#app-component {
  /*font-size: 3em;*/
  background-color: rgb(0, 255, 64);
  padding: 50px;
}
/*this will change the font size for both */

p {
  font-family: 'Courier New', Courier, monospace;
}
#BMIC {
  color: black;
}
#wryAnswer1 {
  color: black;
}


</style>
