<script setup>
import { ref, watch } from 'vue'

defineProps({
  question: String,
  answer1: String,
  answer2: String
})

const emit = defineEmits([
  'stats-entered'
])
// vue wants two answers with a "-" in between


const choice = ref('') // making the radio buttons work correctly

// function choiceMade () {
//   // emit event to tell parent that user has made choice
//   emit('answer-selected', choice.value)
// }

watch(choice, () => {
  emit('stats-entered', choice.value)
})

</script>

<template>

<div id="wyr">

  <h2> Enter your height and weight</h2>
  

  <p> {{ question }} </p>

      <div>
        <!-- making radio buttons-->
        <!-- <input v-model="choice" v-bind:value="answer1" type="radio" id="answer-1"> -->
        <label for="answer-1">{{ answer1 }}</label>
        <input type="text">
        <!-- this value attribute is the HTML value, for what data an input stores-->
        <div>
        <!-- <input v-model="choice" v-bind:value="answer2" type="radio" id="answer-2"> -->
        <label for="answer-2">{{ answer2 }}</label>
        <input type="text">
        </div>
     </div>
    
</div>

<button class="button">Calculate</button>
</template>

<style scoped>
/* #wyr { */
  
/* } */

p {
  font-family: fantasy;
}


</style>
