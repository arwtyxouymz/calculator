<template>
  <div>
    <button @click="pushButton">
      <span>{{ num }}</span>
    </button>  
  </div>
</template>

<script>
export default {
  props: {
    num: {
      type: String,
      default: "",
    }
  },
  methods: {
    pushButton () {
      this.$emit('push-button', this.num)
    }
  }
}
</script>

<style scoped>
*:focus {
  outline: none;
}

button {
  background: #222222;
  color: white;
  font-size: 3em;
  width: 90px;
  height: 90px;
  border-radius: 50%;
  border: none;
  transition: background-color 1.0s;
}

button:hover {
  cursor: pointer;
}

button:active {
  background: rgba(34, 34, 34, .4);
  transition: background-color 0.1s;
}

span {
  margin: auto;
}
</style>
