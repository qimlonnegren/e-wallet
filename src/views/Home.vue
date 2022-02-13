<template>
  <div class="homeView">
    <h1>E-wallet</h1>
    <h6>Active Card</h6>
    <h2 v-if="!activeCard">You have no cards!</h2>
    <Card v-if="activeCard" v-bind:cardInfo="activeCard" />
    <CardList v-bind:cards="cards" @clickedCard="activateCard" />
    <button @click="AddCardView">Add Card</button>
  </div>
</template>

<script>
import Card from "../components/Card";
import CardList from "../components/CardList";
export default {
  components: { Card, CardList },
  props: ["cards"],
  data() {
    return {
      clickedCard: undefined,
    };
  },
  methods: {
    AddCardView() {
      this.$emit("AddCardView");
    },
    activateCard(card) {
      console.log(card);
      this.clickedCard = card;
    },
  },
  computed: {
    activeCard() {
      if (this.clickedCard) {
        return this.clickedCard;
      }
      if (this.cards){
        return this.cards[0]
      }
      return undefined;
    },
  },
};
</script>

<style scoped>
h2 {
  margin-top: 50px;
}
.homeView {
  width: 382px;
  padding-bottom: 50px;
}
button {
  margin-top: 14rem;
}
</style>