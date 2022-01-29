<template>
<div>
    <ul>
        <li v-for="card in this.cards"
        :card="card"
        :key="card.number">
        </li>
    </ul>
</div>
  
</template>

<script>
export default {
    data(){return{
        cards: {'Hello': 'Hello'},
    }}
}
</script>

<style scoped>
div {
    display: inline-flex;
    width: 100%;
}


</style>