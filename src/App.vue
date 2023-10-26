<script setup>
import WouldYouRather from './components/WouldYouRather.vue'


import { ref } from 'vue' // added this 

// creating some reactive statements
const wyrQuestion = ref('Would you rather be incredibly funny or incredibly smart?')
const wryAnswer1 = ref('Incredibly funny')
const wryAnswer2 = ref('Incredibly smart')

// this wil store the user's answer once they made a choice

const userSelection = ref('')

function updateUserSelection(userChoice) {
  userSelection.value = `Thanks! You chose ${userChoice}`
}
// this goes with the function choiceMade on WouldYouRather.vue

</script>

<template>

  <div id="app-component">

  <h1>Would You Rather?</h1>

  <WouldYouRather 
    v-bind:question="wyrQuestion"
    v-bind:answer1="wryAnswer1"
    v-bind:answer2="wryAnswer2"
    v-on:answer-selected="updateUserSelection"
    ></WouldYouRather>
  <!-- you can do multiple v-bind statements -->
  <!-- this will send data to the props -->

   <p> {{ userSelection }} </p>  
</div>

</template>

<style scoped>

#app-component {
  /*font-size: 3em;*/
  background-color: aqua;
  padding: 40px;
}
/*this will change the font size for both */

p {
  font-family: 'Courier New', Courier, monospace;
}


</style>
