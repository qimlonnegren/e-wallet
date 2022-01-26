<template>
  <div class="formSection">
    <Card v-bind:cardInfo="cardInfo" />
    <label for="card-number">Card Number</label>
    <input v-model="cardInfo.number" type="text" id="card-number" name="card-number" placeholder="xxxx xxxx xxxx xxxx"/>
    <label for="cardholder-name">Cardholder Name</label>
    <input v-model="cardInfo.name" type="text" id="cardholder-name" name="cardholder-name" placeholder="Firstname Lastname"/>
    
    <label for="card-month" class="card-month">Month</label>
    <select v-model="cardInfo.month" name="card-month" id="card-month" class="card-month">
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
    
    <label for="card-year" class="card-year">Year</label>
    <select v-model="cardInfo.year" name="card-year" id="card-year" class="card-year">
      <i class="fas fa-chevron-down"></i>
      <option value="blank"></option>
      <option value="21">21</option>
      <option value="22">22</option>
      <option value="23">23</option>
      <option value="24">24</option>
      <option value="25">25</option>
    </select>
    
    <label for="card-type">Bank</label>
    <select v-model="cardInfo.bank" name="card-type" id="card-type">
      <i class="fas fa-chevron-down"></i>
      <option value=""></option>
      <option value="bitcoin-inc">Bitcoin Inc</option>
      <option value="blockchain-inc">Blockchain Inc</option>
      <option value="evil-corp">Evil Corp</option>
      <option value="ninjabank">Ninjabank</option>
    </select>
    
    <button @click="submit">Add Card</button>
    <!-- <p>hello</p> -->
  </div>
</template>

<script>
import Card from './Card'

export default {
    components: {Card},
    data(){return{
      cardInfo: {
        number: '',
        name: '',
        month: '',
        year: '',
        bank: '',
        }
    }}
    methods: {
     submit(){
        
   }
  }
};
</script>

<style>
.formSection{
  display: flex;
  flex-direction: column;
  text-align: left;
  flex-flow: column wrap;
}
label{
    font-size: 12px;
    opacity: 80%;
    margin-top: 10px;
}
.card-month{
    width: 40%;
}
.card-year{
    width: 40%;
}
input, button{
    width: 382px;
    height: 56px;
}
select{
    height: 56px;
}
select, input, button{
    border: 1px solid rgba(0, 0, 0, 0.8);
    border-radius: 8px;
}
</style>