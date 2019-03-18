<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" class="text-center">
    <h1 class="text-center">Currency Converter</h1>

    <div class="line">
      <Converter coin-a="USD" coin-b="BRL"></Converter>
      <Converter coin-a="BRL" coin-b="USD"></Converter>
    </div>

    <div class="line">
      <Converter coin-a="EUR" coin-b="BRL"></Converter>
      <Converter coin-a="BRL" coin-b="EUR"></Converter>
    </div>

    <div class="line">
      <Converter coin-a="CAD" coin-b="BRL"></Converter>
      <Converter coin-a="BRL" coin-b="CAD"></Converter>
    </div>

  </div>
</template>

<script>

import Converter from "./components/Converter";
export default {
  name: 'app',
  components: {
    Converter
  }
}
</script>

<style>
#app {
  max-width: 900px;
  margin: auto;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}
  .line{
    margin-top: 40px;
    display: flex;
    justify-content: space-around;

  }

</style>
