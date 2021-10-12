<template>
  <div id="app">
    <h1 class="text-center">Coversor de Moedas</h1>

    <div class="line">
      <Conversor currency-a="USD" currency-b="BRL"/>
      <Conversor currency-a="BRL" currency-b="USD"/>
    </div>

    <div class="line">
      <Conversor currency-a="CAD" currency-b="BRL"/>
      <Conversor currency-a="BRL" currency-b="CAD"/>
    </div>

    <div class="line">
      <Conversor currency-a="EUR" currency-b="BRL"/>
      <Conversor currency-a="BRL" currency-b="EUR"/>
    </div>

  </div>
</template>

<script>
import Conversor from "./components/Conversor.vue"

export default {
  name: 'App',
  components: {
    Conversor
  }
}
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.line{
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}

.text-center {
  text-align: center;
}
</style>
