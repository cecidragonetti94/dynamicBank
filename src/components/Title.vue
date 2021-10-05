<template>
  <div class="title">
    <h1>{{ text }}</h1>
    <img
      src="https://w7.pngwing.com/pngs/279/210/png-transparent-wire-transfer-bank-account-payment-money-bank-angle-service-logo.png"
      alt=""
    />
  </div>
</template>

<script>
export default {
  name: "Title",
  props: {
    text: String,
  },
};
</script>

<style scoped>
h1 {
  font-weight: bolder;
  font-size: 50px;
}
img {
  border-radius: 50px;
  width: 60px;
  height: 50px;
  display: flex;
  margin-left: 8px;
}
.title {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 176px;
  width: 1880px;
  box-shadow: 5px 4px 5px 0px rgba(73, 67, 67, 0.75);
  -webkit-box-shadow: 5px 4px 5px 0px rgba(148, 127, 127, 0.75);
  -moz-box-shadow: 5px 4px 5px 0px rgba(148, 127, 127, 0.75);
  background-color: lightgrey;
  color: rgb(29, 10, 83);
 
}
</style>