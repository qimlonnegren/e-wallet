<template>
  <div class="addCardView">
    <h1>Add A New Bank Card</h1>
    <h6>New Card</h6>
    <Card v-bind:cardInfo="newCard"/>
    <article class="addCardForm">
      <span>
        <label for="card-number">Card Number</label>
        <input
          v-model="newCard.cardNumber"
          type="text"
          id="card-number"
          name="card-number"
          placeholder="xxxx xxxx xxxx xxxx"
        />
      </span>
      <span>
        <label for="cardholder-name">Cardholder Name</label>
        <input
          v-model="newCard.name"
          type="text"
          id="cardholder-name"
          name="cardholder-name"
          placeholder="Firstname Lastname"
        />
      </span>
      <span class="span-month">
        <label for="card-month" class="card-month">Month</label>
        <br />
        <select
          v-model="newCard.month"
          name="card-month"
          id="card-month"
          class="card-month"
        >
          <i class="fas fa-chevron-down"></i>
          <option value="blank"></option>
          <option value="01">01</option>
          <option value="02">02</option>
          <option value="03">03</option>
          <option value="04">04</option>
          <option value="05">05</option>
          <option value="06">06</option>
          <option value="07">07</option>
          <option value="08">08</option>
          <option value="09">09</option>
          <option value="10">10</option>
          <option value="11">11</option>
          <option value="12">12</option>
        </select>
      </span>
      <span class="span-year">
        <label for="card-year" class="card-year">Year</label>
        <br />
        <select
          v-model="newCard.year"
          name="card-year"
          id="card-year"
          class="card-year"
        >
          <i class="fas fa-chevron-down"></i>
          <option value="blank"></option>
          <option value="21">21</option>
          <option value="22">22</option>
          <option value="23">23</option>
          <option value="24">24</option>
          <option value="25">25</option>
        </select>
      </span>
      <span>
        <label for="card-type">Bank</label>
        <select v-model="newCard.bank" name="card-type" id="card-type">
          <i class="fas fa-chevron-down"></i>
          <option value=""></option>
          <option value="bitcoin-inc">Bitcoin Inc</option>
          <option value="blockchain-inc">Blockchain Inc</option>
          <option value="evil-corp">Evil Corp</option>
          <option value="ninjabank">Ninjabank</option>
        </select>
      </span>

      <button @click="submit">Add Card</button>
      <!-- <input id="submit" type="submit" value="Add Card"/> --> 
    </article>
  </div>
</template>

<script>
import Card from "../components/Card";

export default {
  components: { Card },
  data() {
    return {
      newCard: {
        cardNumber: "",
        name: "",
        month: "",
        year: "",
        bank: "",
      },
    };
  },
  methods: {
    submit() {
      this.$emit("submitCard", this.newCard);
      this.$emit("homeView");
    },
  },
};
</script>

<style>
.addCardView {
  width: 382px;
  padding-bottom: 40px;
}
.addCardForm {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: auto;
  justify-content: space-between;
  column-gap: 10px;
  row-gap: 10px;
}
label {
  font-size: 12px;
  opacity: 80%;
  margin-top: 10px;
}
span {
  grid-column: span 2;
  text-align: left;
}
.span-month {
  grid-column: span 1;
}
.span-year {
  grid-column: span 1;
}
select,
button,
input {
  height: 56px;
  width: 100%;
  border: 1px solid rgba(0, 0, 0, 0.8);
  border-radius: 8px;
}
input {
  border: 1px solid rgba(0, 0, 0, 0.8);
  border-radius: 8px;
  width: 98.5%;
}
button {
  grid-column: span 2;
  background-color: black;
  color: white;
  font-weight: 700;
  font-size: large;
  text-transform: uppercase;
  height: 65px;
  margin-top: 30px;
}
</style>

