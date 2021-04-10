<template>
  <div class="wyr">
    <h2>Please make your choice!</h2>

    <h3>{{ question.question }}</h3>

    <input type="radio" v-model="choice" v-bind:value="question.answer1" v-on:change="choiceMade"
    ><label>{{ question.answer1 }}</label>

    <input type="radio" v-model="choice" v-bind:value="question.answer2" v-on:change="choiceMade"
    ><label>{{ question.answer2 }}</label>


  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    question: Object

    
  },
  data() {
    return {
      choice: ''
    }
  },
  methods: {
    choiceMade() {
      this.$emit('answer-changed', this.choice, this.question.id)
    }
  }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
.wyr {
  border: 2px black solid;
  background: rgb(116, 157, 223);
  margin: 10px
}
</style>
