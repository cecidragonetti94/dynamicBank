<template>
  <div id="app" class="app">
    <Title text=" Dynamic bank"/>
    <Account style="color:blue"/>
  </div>
</template>

<script>
import Account from './components/Account';
import Title from "./components/Title";

export default {
  name: "App",
  components: {
    Title,
    Account,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Abril+Fatface&display=swap');

*{
  font-family: 'Abril Fatface', cursive;
  
  }
.app{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  
}
body{
  background: rgb(2,0,36);
background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(212,212,223,0.227328431372549) 23%, rgba(138,142,177,0.6867121848739496) 100%);
}
</style>
