<template>
  <div>
      <h1>E-wallet</h1>
      <h6>Active Card</h6>
      <Card/>
      <!-- <AddCardForm @submitCard="reciveCard" /> -->
  </div>
</template>

<script>
import Card from '../components/Card'
// import AddCardForm from '../components/AddCardForm'
export default {
    components: {Card},

    methods: {
      reciveCard(){
       console.log('Helooo') 
      }
   }
}
</script>

<style>

</style>