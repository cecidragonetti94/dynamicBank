<template>
  <div class="container-account">
    <div class="account-select">
      <h2>Account type: {{ account }}</h2>

      <select name="tarjetas" class="cards">
        <option>MasterCard</option>
        <option>AmericanExpress</option>
        <option>Visa</option>
      </select>
    </div>

    <h2> balance: <span :style="[balance > 400 ? {'color': 'green'} : {'color': 'red'} ]"> {{ balance }}</span></h2>
    <hr /> 
    <h2>Account: <span style="color:green">{{ status ? "Activated" : "Disabled" }}</span> </h2>
    <div v-for="(service, index) in services" :key="index">
      {{ index + 1 }} {{ service }}
    </div>
    <hr />
   <div class="container-button">
  
    <ActionBalance text="increase balance" @action="increase" />
    <ActionBalance
      text="decrease balance"
      @action="decrease"
      :desactivate="desactivate"
    />
       
   </div>
  </div>
</template>

<script>
import ActionBalance from "./ActionBalance";

export default {
  components: {
    ActionBalance,
  },
  data: () => ({
    balance: 1000,
    //account: "Visa",
    status: true,
    services: ["order", "payment", "transference"],
    desactivate: false,
  }),
  methods: {
    increase() {
      this.balance += 100;
      this.desactivate = false;
    },
    decrease() {
      if (this.balance === 0) {
        this.desactivate = true;
        alert(" depleted balance");
      } else {
        this.balance -= 100;
      }
    },
  },
};
</script>

<style>
* {
  color: rgb(29, 10, 83);
}
.account-select {
  display: flex;
  flex-direction: row;
  text-align: center;
  justify-content: center;
}

.container-account {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 500px;
  box-shadow: 0px 4px 5px 0px rgba(148, 127, 127, 0.75);
  -webkit-box-shadow: 0px 4px 5px 0px rgba(148, 127, 127, 0.75);
  -moz-box-shadow: 0px 4px 5px 0px rgba(148, 127, 127, 0.75);
  width: 900px;
  margin-top: 10px;
  background-color: snow;
  border-radius: 10px;
}
.cards {
  height: 35px;
  width: 135px;
  margin-top: 19px;
  margin-left: 8px;
}
.container-button {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  width: 615px;
  height: 40px;
  font-size: 30px;
}
button:hover {
  background-color: rgb(29, 10, 83);
  color: white;
}
</style>