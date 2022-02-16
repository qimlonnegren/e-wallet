<template>
  <div>
    <article class="card" :class="cardInfo.bank">
      <img v-if="cardInfo.bank == 'block-chain-card'" src="../assets/wifi_white.svg" alt="White wifi logo" class="wifi-img" />
      <img v-else-if="cardInfo.bank == 'evil-corp-card'" src="../assets/wifi_white.svg" alt="White wifi logo" class="wifi-img" />
      <img v-else-if="cardInfo.bank == 'ninja-bank-card'" src="../assets/wifi_white.svg" alt="White wifi logo" class="wifi-img" />
      <img v-else src="../assets/wifi.svg" alt="Wifi image" class="wifi-img" />

      <br />
  
      <div v-if="cardInfo.bank == 'bitcoin-card'" class="vendor-img bitcoin-logo"></div>
      <div v-if="cardInfo.bank == 'block-chain-card'" class="vendor-img block-chain-logo"></div>
      <div v-if="cardInfo.bank == 'evil-corp-card'" class="vendor-img evil-corp-logo"></div>
      <div v-if="cardInfo.bank == 'ninja-bank-card'" class="vendor-img ninja-bank-logo"></div>

      <img src="../assets/chip.svg" alt="Chip image" class="chip-img" />

      <h2 v-if="cardInfo.cardNumber == 0"
      class="cardNumber"
      >
        xxxx xxxx xxxx xxxx
      </h2>
      <h2 v-else class="cardNumber"
      >{{ displayCardNumber }}</h2>
      <h3
      >Cardholder Name</h3>
      <p v-if="cardInfo.name == 0"
      >Firstname Lastname</p>
      <p v-else
      >{{ cardInfo.name }}</p>
      <h3 class="rightInfo rightH3"
      >Valid Thru</h3>
      <p class="rightInfo rightP"
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
    // changeTextColor() {

    // }
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

.bitcoin-card {
  background: linear-gradient(60deg, #ffae34 78%, rgba(255, 255, 255, 0.15));
  background-color: #ffae34;
  color: #222222;
}
.ninja-bank-card {
  background: linear-gradient(60deg, #222222 78%, rgba(255, 255, 255, 0.15));
  background-color: #222222;
  color: rgb(224, 224, 222);
}
.block-chain-card {
  background: linear-gradient(60deg, #8b58f9 78%, rgba(0, 0, 0, 0.15));
  background-color: #8b58f9;
  color: rgb(224, 224, 222);
}
.evil-corp-card {
  background: linear-gradient(60deg, #f33355 78%, rgba(0, 0, 0, 0.15));
  background-color: #f33355;
  color: rgb(224, 224, 222);
}
.bitcoin-logo {
  background-image: url("../assets/bitcoin.svg");
}
.ninja-bank-logo {
  background-image: url("../assets/ninja.svg");
}
.block-chain-logo {
  background-image: url("../assets/blockchain.svg");
}
.evil-corp-logo {
  background-image: url("../assets/evil.svg");
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
  bottom: 54px;
}
.rightP {
  bottom: 11px;
  width: 54px;
}
.cardNumber {
  height: 32px;
}
</style>