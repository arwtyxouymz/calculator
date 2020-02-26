<template>
  <TapButton num="=" v-on:push-button="pushButton"/>
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

</style>
