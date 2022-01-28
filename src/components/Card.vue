<template>
  <div>
      <article class="card">
          <img src="../assets/wifi.svg" alt="White wifi logo" class="wifi-img">
          <br>
          <!-- <img src="../assets/bitcoin.svg" alt="Bitcoin image" class="vendor-img"> -->
            <div class="vendor-img bitcoin"></div>
          <img src="../assets/chip.svg" alt="Chip image" class="chip-img">
          <h2 v-if="cardInfo.number == 0" class="cardNumber">xxxx xxxx xxxx xxxx</h2>
          <h2 v-else class="cardNumber">{{cardInfo.number}}</h2>
          <h3>Cardholder Name</h3>
          <p v-if="cardInfo.name == 0">Firstname Lastname</p>
          <p v-else>{{cardInfo.name}}</p>
          <h3 class="rightInfo rightH3">Valid Thru</h3>
          <p class="rightInfo rightP">{{cardInfo.month}}/{{cardInfo.year}}</p>
      </article>
  </div>
</template>

<script>
export default {
    props: ['cardInfo']
}
</script>

<style>
.card{
width: 352px;
height: 201px;
border: 0px;
border-radius: 8px;
background-color: #D0D0D0;
padding: 15px;
position: relative;
text-align: left;
}
h2{
    font-size: 29px;
    margin: 10px 0 25px 0;
    font-weight: 500;
}
h3{
    font-size: 12px;
    margin: 0;
}
p{
    font-size: 18px;
    margin-top: 5px;
}
.wifi-img{
    height: 44px;
    width: 44px;
    position: relative;
    top: 0;
    left: 0;
    padding-left: 3px;
}
.vendor-img{
    height: 64px;
    width: 64px;
    position: absolute;
    top: 10px;
    right: 5px;
    text-align: left;
}
.chip-img{
    height: 40px;
    width: 50px;
    position: relative;
    top: 0;
    left: 0;
}
.rightInfo{
    position: absolute;
    right: 15px;
}
.rightH3{
bottom: 44px;
}
.rightP{
bottom: 0px;
width: 54px;
}
.cardNumber{
height: 32px;
}
.bitcoin{
background-image: url('../assets/bitcoin.svg');
background-color: #FFAE34;
}
.ninja-bank{
    background-image: url('../assets/ninja.svg');
    background-color: black;
}
.block-chain{
    background-image: url('../assets/blockchain.svg');
    background-color: purple;
}
.evil-corp{
    background-image: url('../assets/evil.svg');
    background-color: red;
}
</style>