<template>
<div>
    <ul v-if="cards">
        <li v-for="card in cards"
        :key="card.cardNumber"
        @click="activateCard(card)">
    
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

    }},
    methods: {
        activateCard(card){
            //console.log(card)
            this.$emit("clickedCard", card);
        }
    }
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
    grid-auto-rows: 50px;
}
li{
    list-style-type: none;
}
</style>