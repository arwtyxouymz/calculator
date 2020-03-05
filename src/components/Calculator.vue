<template>
  <div>
    <header>
      <h1>Vue.js Calculator</h1>
    </header>
    <div class="calculator">
      <div class="display" ref="boxWrapper">
        <p :style="fontScale" ref="autoScaleText">{{ display }}</p>
      </div>
      <div class="field">
        <TapButton @push-button="clear" value="AC" kind="other"/>
        <TapButton @push-button="changeSign" value="+/-" kind="other"/>
        <TapButton @push-button="percent" value="%" kind="other"/>
        <TapButton @push-button="operatorAdd" value="÷" kind="operator"/>
        <TapButton @push-button="numericAdd" value="7"/>
        <TapButton @push-button="numericAdd" value="8"/>
        <TapButton @push-button="numericAdd" value="9"/>
        <TapButton @push-button="operatorAdd" value="×" kind="operator"/>
        <TapButton @push-button="numericAdd" value="4"/>
        <TapButton @push-button="numericAdd" value="5"/>
        <TapButton @push-button="numericAdd" value="6"/>
        <TapButton @push-button="operatorAdd" value="-" kind="operator"/>
        <TapButton @push-button="numericAdd" value="1"/>
        <TapButton @push-button="numericAdd" value="2"/>
        <TapButton @push-button="numericAdd" value="3"/>
        <TapButton @push-button="operatorAdd" value="+" kind="operator"/>
        <TapButton class="zero" @push-button="numericAdd" value="0"/>
        <TapButton @push-button="addDot" value="."/>
        <TapButton @push-button="equal" value="=" kind="operator"/>
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
      current: "0",
      previous: null,
      operator: null,
      scale: 1.0
    }
  },
  computed: {
    display () {
      return Number(this.current).toString()
    },
    fontScale () {
      return { transform: `scale(${this.scale}, ${this.scale})` }
    }
  },
  watch: {
    display: function () {
      this.$nextTick(function () {
        const boxWrapper = this.$refs.boxWrapper.offsetWidth
        const autoScaleText = this.$refs.autoScaleText.offsetWidth
        const scale = boxWrapper / autoScaleText
        if (scale < 1.) {
          this.scale = scale
        } else {
          this.scale = 1.0
        }
      })
    }
  },
  methods: {
    numericAdd ({ value }) {
      if (this.operator !== null && this.previous === null) {
        this.previous = this.display
        this.current = ""
      }
      this.current += value
    },
    operatorAdd ({ value }) {
      if (value === "+") {
        this.operator = (a, b) => a + b
      } else if (value === "-") {
        this.operator = (a, b) => a - b
      } else if (value === "×") {
        this.operator = (a, b) => a * b
      } else if (value === "÷") {
        this.operator = (a, b) => a / b
      }
    },
    clear (_value) {
      this.current = "0"
      this.operator = null
      this.previous = null
    },
    percent (_value) {
      this.current = Number(this.current) / 100.0
    },
    equal (_value) {
      if (this.operator !== null) {
        this.current = this.operator(
          Number(this.previous), Number(this.current))
        this.operator = null
        this.previous = 0
      }
    },
    changeSign (_value) {
      this.current = -1 * this.current
    },
    addDot (_value) {
      this.current += "."
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

.display {
  height: 20%;
  position: relative;
}

.display p {
  color: white;
  text-align: left;
  font-size: calc(3vw + 30px);
  font-weight: bold;
  margin: 0;
  position: absolute;
  bottom: 0;
  right: 0;
  padding-right: 0.5em;
  padding-left: 0.5em;
  transform-origin: right;
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

  .display p {
    font-size: 4.5em;
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
