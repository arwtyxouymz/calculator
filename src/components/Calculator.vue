<template>
  <div>
    <header>
      <h1>Vue.js Calculator</h1>
    </header>
    <div class="calculator">
      <div class="result">
        <p>4,339</p>
      </div>
      <div class="field">
        <TapButton num="AC"/>
        <TapButton num="+/-"/>
        <TapButton num="%"/>
        <TapButton num="÷"/>
        <TapButton num="7"/>
        <TapButton num="8"/>
        <TapButton num="9"/>
        <TapButton num="×"/>
        <TapButton num="4"/>
        <TapButton num="5"/>
        <TapButton num="6"/>
        <TapButton num="-"/>
        <TapButton num="1"/>
        <TapButton num="2"/>
        <TapButton num="3"/>
        <TapButton num="+"/>
        <TapButton num="0"/>
        <TapButton num="0"/>
        <TapButton num="."/>
        <TapButton num="="/>
      </div>
    </div>
  </div>
</template>

<script>
import TapButton from '@/components/TapButton.vue'
export default {
  components: {
    TapButton
  },
  methods: {
    pushButton: function (data) {
      console.log(data)
    }
  }
}
</script>

<style scoped>
header {
  box-sizing: border-box;
  height: 10%;
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin: 10px;
}

h1 {
  font-size: calc(1vw + 30px);
  margin: 0;
  color: white;
}

div.calculator {
  background-color: black;
  box-sizing: border-box;
  width: 100%;
  height: 85%;
  margin: 0 auto;
}

.result {
  height: 20%;
  position: relative;
}

.result p {
  color: white;
  text-align: right;
  font-size: calc(3vw + 30px);
  font-weight: bold;
  margin: 0;
  position: absolute;
  bottom: 0;
  right: 0;
  padding-right: 0.5em;
}

div.field {
  box-sizing: border-box;
  height: 80%;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  /* grid-column-gap: 20px; */
  padding: 10px;
}

@media (min-width: 425px) {
  header h1 {
    font-size: 3em;
  }

  .result p {
    font-size: 3.5em;
  }

  div.calculator {
    width: 410px;
  }
}

@media (min-width: 600px) {
  div.calculator {
    width: 420px;
  }
}
</style>
