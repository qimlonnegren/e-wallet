<template>
  <div id="app">
    <Home @AddCardView="homeView = false" v-if="homeView" />
    <AddCard @homeView="homeView = true" @submitCard="reciveCard" v-else />
    <CardList v-if="homeView"/>
    <p>{{cards}}</p>
  </div>
</template>

<script>
import Home from './views/Home'
import AddCard from './views/AddCard'
import CardList from './components/CardList'


export default {
  components: {Home, AddCard, CardList},
  data(){return{
    homeView: true,
    
    cards: [],
  }},
  methods: {
      reciveCard(a){
      console.log(a)
      console.log('Helooo')
      this.cards.push(a)
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
  background-color: palevioletred;
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
</style>