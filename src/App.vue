<template>
  <div id="app">
    <Calculator />
  </div>
</template>

<script>
import Calculator from '@/components/Calculator.vue'
export default {
  name: 'app',
  components: {
    Calculator
  }
}
</script>

<style>
html,
body {
  height: 100%;
  background-color: #202f55;
}

div {
  height: 100%;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  height: 100%;
}
</style>
