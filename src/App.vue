<template>
  <div id="app">
    <img src="./assets/logo.png">
    <calculator msg="Made with Vue"/>
  </div>
</template>

<script>
import calculator from './components/calculator.vue'

export default {
  name: 'app',
  components: {
    calculator
  }
}
</script>

<style>

body {
  width: 90%;
  max-width: 960px;
  margin: 0 auto;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  text-align: center;
}
</style>
