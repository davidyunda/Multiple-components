<template>
  <div id="app">
    <h1>Would you rather</h1>

    <!-- Duplicate 3 times -->
    <would-you-rather v-for="question in questions" v-bind:key="question.id"
    v-bind:question="question"
    v-on:answer-changed="answerChanged"
    ></would-you-rather>

    <!-- display message -->
    <li v-for="choice in choicesMade">{{ choice }}</li>
    
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
          answer1: 'dance',
          answer2: 'sing'
        },
        {
          id: 1,
          question: 'Would you rather see a firework display or a circus performance?',
          answer1: 'firework display',
          answer2: 'circus performance'
        },
        {
          id: 2,
          question: 'Would you rather be able to create a new holiday or create a new sport?',
          answer1: 'create new holiday',
          answer2: 'create new sport'
        }
      ],
      choices: [],
      userSelectionMessage: ''
    }
  },
  methods: {
    answerChanged(choice, id) {
      // this.userSelectionMessage = `You Would Rayher... ${choice}`
      // console.log(choice, id)
      this.choices[id] = choice
    }
  },
  computed: {
    choicesMade() {
      let userChoices = []
      this.choices.forEach( c => {
        if (c) {
          userChoices.push(c)
        }
      } )
      return userChoices
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

