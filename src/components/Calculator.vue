<template>
  <div>
    <header>
      <h1>Vue.js Calculator</h1>
    </header>
    <div class="calculator">
      <div class="result">
        <p>{{ result }}</p>
      </div>
      <div class="field">
        <TapButton @push-button="pushButton" value="AC" kind="other"/>
        <TapButton @push-button="pushButton" value="+/-" kind="other"/>
        <TapButton @push-button="pushButton" value="%" kind="other"/>
        <TapButton @push-button="pushButton" value="÷" kind="operator"/>
        <TapButton @push-button="pushButton" value="7"/>
        <TapButton @push-button="pushButton" value="8"/>
        <TapButton @push-button="pushButton" value="9"/>
        <TapButton @push-button="pushButton" value="×" kind="operator"/>
        <TapButton @push-button="pushButton" value="4"/>
        <TapButton @push-button="pushButton" value="5"/>
        <TapButton @push-button="pushButton" value="6"/>
        <TapButton @push-button="pushButton" value="-" kind="operator"/>
        <TapButton @push-button="pushButton" value="1"/>
        <TapButton @push-button="pushButton" value="2"/>
        <TapButton @push-button="pushButton" value="3"/>
        <TapButton @push-button="pushButton" value="+" kind="operator"/>
        <TapButton class="zero" @push-button="pushButton" value="0"/>
        <TapButton @push-button="pushButton" value="."/>
        <TapButton @push-button="pushButton" value="=" kind="operator"/>
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
  data () {
    return {
      result: 0,
    }
  },
  methods: {
    pushButton: function ({ kind, value }) {
      console.log(kind, value);
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
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 10px;
  padding: 10px;
}

.zero {
  grid-column: 1 / 3;
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
