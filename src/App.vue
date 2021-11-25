<template>
  <div id="app">
  <h1>Would you rather....</h1>
    <WouldYouRather v-bind:question="wyrQuestion"
                    v-bind:answer1="wyrAnswer1"
                    v-bind:answer2="wyrAnswer2"
                    v-on:answer-changed="answerChanged"></WouldYouRather>

    <p>{{ userSelectionMessage }}</p>

  </div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data(){
    return {
      wyrQuestion:'Would you rather live in a house shaped like a circle or a house shaped like a triangle?',
      wyrAnswer1:'circle',
      wyrAnswer2:'triangle',
      userSelectionMessage:'',
    }
  },
  methods:{
    answerChanged(choice){
      this.userSelectionMessage=`Thanks! You chose ${choice}`
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  margin-top: 60px;
  background: blueviolet;
}

p{
  font-style: italic;
}
</style>
