<template>
  <div>
    <button :class="kind" @click="pushButton">
      <span>{{ value }}</span>
    </button>  
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      default: "",
    },
    kind: {
      type: String,
      default: "numeric"
    }
  },
  methods: {
    pushButton () {
      this.$emit('push-button', { kind: this.kind, value: this.value })
    }
  }
}
</script>

<style scoped>
*:focus {
  outline: none;
}

button {
  position: relative;
  font-size: 2.8em;
  width: 100%;
  height: 100%;
  border: none;
  transition: background-color 1.0s;
}

button.numeric {
  background-color: #222222;
  color: white;
}

button.operator {
  background-color: orange;
  color: white;
  font-size: 3.5em;
}

button.other {
  background-color: #A9A9A9;
  color: black;
  font-size: 2.3em;
}

button:hover {
  cursor: pointer;
}

button:active {
  transition: background-color 0.1s;
}

button.numeric:active {
  background-color: rgba(255, 255, 255, .4);
}

button.operator:active {
  background-color: rgba(255, 255, 255, .9);
  color: orange;
}

button.other:active {
  background-color: white;
}

span {
  margin: auto;
}
</style>
