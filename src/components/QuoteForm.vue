<template>
  <div class="form">
    <div class="form-group">
      <label for="quote">Don't quote me on this:</label>
      <textarea v-model="quote.message"
        id="quote"
        name="quote"
        class="form-control"
        rows="5"
        @keyup.enter="quoteMe">
      </textarea>
    </div>
    <button :disabled="quote.message === ''"
      class="btn btn-primary btn-block"
      @click="quoteMe">
      Quote Me
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quote: {
        message: "",
        id: 0
      }
    }
  },
  methods: {
    quoteMe() {
      // https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random
      let min = 4;
      let max = Number.MAX_SAFE_INTEGER;
      let id =  Math.floor(Math.random() * (max - min)) + min;
      let quote = this.quote.message;
      this.$emit('quoteWasAdded', {
        message: quote,
        id: id
      })
      this.quote = {
        message: "",
        id: 0
      }
    }
  }
}
</script>

<style scoped>
.form {
  width: 50%;
  display: block;
  margin: 15px auto;
}
</style>
