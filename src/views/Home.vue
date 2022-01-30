<template>
  <div class="homeView">
      <h1>E-wallet</h1>
      <h6>Active Card</h6>
      <h2 v-if="this.activeCard == undefined">You have no cards!</h2>
      <Card v-if="this.cards[0]" v-bind:cardInfo="this.cards[0]"/>
      <CardList v-bind:cards="this.cards" />
      <button @click="AddCardView">Add Card</button>
  </div>
</template>

<script>
import Card from '../components/Card'
import CardList from '../components/CardList'
export default {
    components: {Card, CardList},
    props: ['cards'],
    data(){return{
      activeCard: this.cards[0],
    }},
    methods: {
      AddCardView(){
        this.$emit('AddCardView')
      }
   }
}
</script>

<style scoped>
h2{
  margin-top: 50px;
}
.homeView{
  width: 382px;
  padding-bottom: 50px;
}
button{
  margin-top: 14rem;
}
</style>