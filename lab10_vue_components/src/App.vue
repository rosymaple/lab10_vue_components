<script setup>

import { ref } from 'vue'
import WouldYouRather from './components/WouldYouRather.vue'
// importing child components from WouldYouRather.vue

// data for the question, and two answers
const wyrQuestion = ref('Live in a house shaped like a triangle house or like a circle?')
const answer1 = ref('Triangle house')
const answer2 = ref('Circle house')

// Will store the user's selection, either 'triangle house' or 'circle house'
const userSelection = ref('')

// a function with userChoice as our parameter
// this function will serve to print a message for our user...
// telling user which checkbox they chose.
function updateUserSelection(userChoice) {
  userSelection.value = `Thanks! You chose ${userChoice}!`
}

</script>

<template>

  <div id="app-component">

  <h1>Would You Rather...</h1>

    <!-- imported WouldYouRather component -->
    <!-- binding question prop to wyrQuestion-->
    <!-- answer-selected is an event -->
  <WouldYouRather
    v-bind:question = "wyrQuestion"
    v-bind:answer1 = "answer1"
    v-bind:answer2 = "answer2"
    v-on:answer-selected="updateUserSelection">
    </WouldYouRather>

  <!-- TODO show user's choice from the would-you-rather question -->
    <!-- if user makes a selection, this paragraph will appear-->
    <p v-if="userSelection">{{ userSelection }}</p>

  </div>

</template>

<style scoped>

#app-component {
  /* font-size: 3em */
  background-color: aqua;
  padding: 40px;
}

</style>
