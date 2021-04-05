<template>
  <div class="wyr">
    <h2>Please make your choice!</h2>

    
    <div>
    <h4>{{ question[0].question }}</h4>
    <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="choiceMade"
    ><label>{{ answer1 }}</label>


    <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change="choiceMade"
    ><label>{{ answer2 }}</label>
    </div>


    <div>
    <h4>{{ question[1].question }}</h4>
    <input type="radio" v-model="choice" v-bind:value="answer3" v-on:change="choiceMade"
    ><label>{{ answer3 }}</label>


    <input type="radio" v-model="choice" v-bind:value="answer4" v-on:change="choiceMade"
    ><label>{{ answer4 }}</label>
    </div>

    <div>
    <h4>{{ question[2].question }}</h4>
    <input type="radio" v-model="choice" v-bind:value="answer5" v-on:change="choiceMade"
    ><label>{{ answer5 }}</label>


    <input type="radio" v-model="choice" v-bind:value="answer6" v-on:change="choiceMade"
    ><label>{{ answer6 }}</label>
    </div>
    

  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    question: String,
    answer1: String,
    answer2: String,
    answer3: String,
    answer4: String,
    answer5: String,
    answer6: String,
  },
  data() {
    return {
      choice: []
    }
  },
  methods: {
    choiceMade() {
      this.$emit('answer-changed', this.choice)
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
