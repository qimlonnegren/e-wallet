<template>
<div>
    <ul>
        <li v-for="card in this.cards"
        :key="card.cardNumber">

        <Card v-bind:cardInfo="card"/>
        </li>
    </ul>
</div>
  
</template>

<script>
import Card from '../components/Card'
export default {
    components: {Card},
    props: ['cards'],
    data(){return{

    }}
}
</script>

<style scoped>
div {
    display: inline-flex;
    width: 100%;
}
ul{
    padding: 10px 0 0 0;
    display: grid;
    grid-auto-rows: 35px;
}
li{
    list-style-type: none;
}
</style>