<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/be_nerd_be_strong_logo.png" height="250" width="250">
    <BMI msg="Welcome to Simple BMI App"/>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import BMI from './components/BMI.vue'

export default {
  name: 'app',
  components: {
    BMI
  }
}
</script>

<style>
@import url(https://fonts.googleapis.com/css?family=Roboto:400,500&subset=latin,latin-ext);
#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
