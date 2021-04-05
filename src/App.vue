<template>
  <div id="app">
    <h1>Would you rather</h1>

    <would-you-rather v-bind:question="questions"


    v-bind:answer1="questions[0].answerOne"
    v-bind:answer2="questions[0].answerTwo"

    v-bind:answer3="questions[1].answerOne"
    v-bind:answer4="questions[1].answerTwo" 

    v-bind:answer5="questions[2].answerOne"
    v-bind:answer6="questions[2].answerTwo"  

    v-on:answer-changed="answerChanged"></would-you-rather>


    <p>{{ userSelectionMessage}}</p>
  </div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data() {
    return {
      questions: [
        {
          id: 0,
          question: 'Would you rather dance or sing?',
          answerOne: 'dance',
          answerTwo: 'sing'
        },
        {
          id: 1,
          question: 'Would you rather see a firework display or a circus performance?',
          answerOne: 'firework display',
          answerTwo: 'circus performance'
        },
        {
          id: 2,
          question: 'Would you rather be able to create a new holiday or create a new sport?',
          answerOne: 'create new holiday',
          answerTwo: 'create new sport'
        }
      ],
      userSelectionMessage: ''
    }
  },
  methods: {
    answerChanged(choice) {
      this.userSelectionMessage = `You Would Rayher... ${choice}`
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=New+Tegomin&display=swap');

body {
  background:white
}

#app {
  font-family: new tegomin, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #14212e;
  margin-top: 60px;
  background: rgb(180, 202, 79)
}
</style>

