<template>
  <div>
      <h1>E-wallet</h1>
      <h6>Active Card</h6>
      <Card v-bind:cardInfo="activeCard"/>
      <button @click="AddCardView">Add Card</button>
  </div>
</template>

<script>
import Card from '../components/Card'
export default {
    components: {Card},
    props: ['cards'],
    data(){return{
      activeCard: this.cards[0]
    }},
    methods: {
      AddCardView(){
        this.$emit('AddCardView')
      }
   }
}
</script>

<style>

</style>