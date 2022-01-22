<template>
  <div>
      <h1>Add A New Bank</h1>
      <h6>Active Card</h6>
      <Card/>
      <AddCardForm/>
  </div>
</template>

<script>
import Card from '../components/Card'
import AddCardForm from '../components/AddCardForm'
export default {
    components: {AddCardForm, Card},
    data(){return{

    }}
}
</script>

<style>

</style>