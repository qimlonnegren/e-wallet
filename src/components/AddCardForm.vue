<template>
  <div>
    <label for="card-number">Card Number</label>
    <br>
    <input type="text" id="card-number" name="card-number" placeholder="xxxx xxxx xxxx xxxx"/>
    <br>
    <label for="cardholder-name">Cardholder Name</label>
    <br>
    <input type="text" placeholder="Firstname Lastname"/>
    <br>
    <label for="card-month">Month</label>
    <select name="card-month" id="card-month">
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
    <br>
        <label for="card-year">Year</label>
    <select name="card-year" id="card-year">
      <option value="blank"></option>
      <option value="21">21</option>
      <option value="22">22</option>
      <option value="23">23</option>
      <option value="24">24</option>
      <option value="25">25</option>
    </select>
    <br>
        <label for="card-type">Bank</label>
    <select name="card-type" id="card-type">
        <i class="fas fa-chevron-down"></i>
      <option value=""></option>
      <option value="">Bitcoin Inc</option>
      <option value="dog">Blockchain Inc</option>
      <option value="cat">Evil Corp</option>
      <option value="cat">Ninjabank</option>
    </select>
    <br>
    <button>Add Card</button>
    <!-- <p>hello</p> -->
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>