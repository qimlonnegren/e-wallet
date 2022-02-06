<template>
  <div>
    <article class="card" :class="cardInfo.bank">
      <img src="../assets/wifi.svg" alt="White wifi logo" class="wifi-img" />
      <br />
      <!-- <img src="../assets/bitcoin.svg" alt="Bitcoin image" class="vendor-img"> -->
      <div class="vendor-img bitcoin-logo"></div>
      <img src="../assets/chip.svg" alt="Chip image" class="chip-img" />
      <h2 v-if="cardInfo.cardNumber == 0"
      class="cardNumber"
      :class="'' || bitcoin-card ? 'dark-text' : 'light-text'"
      >
        xxxx xxxx xxxx xxxx
      </h2>
      <h2 v-else class="cardNumber"
      :class="'' || bitcoin-card ? 'dark-text' : 'light-text'"
      >{{ displayCardNumber }}</h2>
      <h3
      :class="'' || bitcoin-card ? 'dark-text' : 'light-text'"
      >Cardholder Name</h3>
      <p v-if="cardInfo.name == 0"
      :class="'' || bitcoin-card ? 'dark-text' : 'light-text'"
      >Firstname Lastname</p>
      <p v-else
      :class="'' || bitcoin-card ? 'dark-text' : 'light-text'"
      >{{ cardInfo.name }}</p>
      <h3 class="rightInfo rightH3"
      :class="'' || bitcoin-card ? 'dark-text' : 'light-text'"
      >Valid Thru</h3>
      <p class="rightInfo rightP"
      :class="'' || bitcoin-card ? 'dark-text' : 'light-text'"
      >{{ cardInfo.month }}/{{ cardInfo.year }}</p>
    </article>
  </div>
</template>

<script>
export default {
  props: ["cardInfo"],
  computed: {
    displayCardNumber() {
      let numbers = "";
      for (let i = 0; i < this.cardInfo.cardNumber.length; i++) {
        numbers += this.cardInfo.cardNumber[i];
        if (i % 4 == 3) {
          numbers += " ";
        }
      }
      return numbers;
    },
  },
};
</script>

<style>
.card {
  width: 352px;
  height: 211px;
  border: 0px;
  border-radius: 8px;
  background-color: #d0d0d0;
  padding: 15px;
  position: relative;
  text-align: left;
  filter: drop-shadow(0 0 16px rgba(0, 0, 0, 0.08));
}

.dark-text{
  background-color: #000000;
  color: transparent;
  text-shadow: 0px 2px 3px rgba(255, 255, 255, 0.5);
  -webkit-background-clip: text;
  -moz-background-clip: text;
  background-clip: text;
}
.light-text{
  background-color: #ffffff;
  color: transparent;
  text-shadow: 0px 2px 3px rgba(255, 255, 255, 0.5);
  -webkit-background-clip: text;
  -moz-background-clip: text;
  background-clip: text;
}

.bitcoin-card {
  background: linear-gradient(60deg, #ffae34 78%, rgba(255, 255, 255, 0.15));
  background-color: #ffae34;
}
.ninja-bank-card {
  background: linear-gradient(60deg, #222222 78%, rgba(255, 255, 255, 0.15));
  background-color: #222222;
}
.block-chain-card {
  background: linear-gradient(60deg, #8b58f9 78%, rgba(255, 255, 255, 0.15));
  background-color: #8b58f9;
}
.evil-corp-card {
  background: linear-gradient(60deg, #f33355 78%, rgba(255, 255, 255, 0.15));
  background-color: #f33355;
}
.bitcoin-logo {
  background-image: url("../assets/bitcoin.svg");
}
.ninja-bank-logo {
  background-image: url("../assets/ninja.svg");
  background-color: black;
}
.block-chain-logo {
  background-image: url("../assets/blockchain.svg");
  background-color: purple;
}
.evil-corp-logo {
  background-image: url("../assets/evil.svg");
  background-color: red;
}

h2 {
  font-size: 29px;
  margin: 10px 0 25px 0;
  font-weight: 500;
}
h3 {
  font-size: 12px;
  margin: 0;
}
p {
  font-size: 18px;
  margin-top: 5px;
}
.wifi-img {
  height: 44px;
  width: 44px;
  position: relative;
  top: 0;
  left: 0;
  padding-left: 3px;
}
.vendor-img {
  height: 64px;
  width: 64px;
  position: absolute;
  top: 10px;
  right: 5px;
  text-align: left;
}
.chip-img {
  height: 40px;
  width: 50px;
  position: relative;
  top: 0;
  left: 0;
}
.rightInfo {
  position: absolute;
  right: 15px;
}
.rightH3 {
  bottom: 44px;
}
.rightP {
  bottom: 0px;
  width: 54px;
}
.cardNumber {
  height: 32px;
}
</style>