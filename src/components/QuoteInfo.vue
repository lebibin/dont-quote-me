<template>
  <div class="bg-info" @click="surpriseMe">
    <p>
      {{ info  }}
    </p>
  </div>
</template>

<script>
import { quotes } from './../data/quotes'
export default {
  data() {
    return {
      info: "Info: Click on a Quote to delete it!"
    }
  },
  methods: {
    surpriseMe() {
      // https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random
      let min = 0;
      let max = quotes.length;
      let index =  Math.floor(Math.random() * (max - min)) + min;
      let quote = quotes[index]
      this.$emit('quoteWasAdded', quote)
    }
  }
}
</script>

<style scoped>
div {
  margin-bottom: 25px;
  height: 50px;
  border-radius: 5px;
}
p {
  padding: 15px;
  text-align: center;
  color: #337ab7;
}
</style>
