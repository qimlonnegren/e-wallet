<template>
  <div id="app">
    <Home @AddCardView="homeView = false" v-if="homeView" v-bind:cards="cards" />
    <AddCard @homeView="homeView = true" @submitCard="reciveCard" v-else />

  </div>
</template>

<script>
import Home from './views/Home'
import AddCard from './views/AddCard'

export default {
  components: {Home, AddCard},
  data(){return{
    homeView: true,
    
    cards: [],
  }},
  methods: {
      reciveCard(a){
        this.cards.push(a)
        // console.log(this.cards)
      },
   }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=PT+Mono&family=Source+Sans+Pro:wght@400;600;700&display=swap");
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css");
#app {
  font-family: "PT Mono", monospace;
  text-align: center;
  width: 414px;
  height: auto;
  margin: auto;
  padding-top: 20px;
  text-transform: uppercase;
  background-color: rgb(255, 255, 255);
  display: flex;
  justify-content: flex-start;
  flex-direction: column;
  align-content: center;
  align-items: center;
}
h1,
h6 {
  font-family: "Source Sans Pro", sans-serif;
}

h1 {
  font-weight: 700;
  margin: 1rem auto 1rem auto;
  width: 162px;
  line-height: 30px;
}
h6 {
  margin: 0.5rem auto 0.3rem auto;
}
button{
  width: 380px;
}
body{
  background-color: lightgray;
}
</style>