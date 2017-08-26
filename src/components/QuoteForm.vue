<template>
  <div class="form">
    <div class="form-group">
      <label for="quote">Don't quote me on this:</label>
      <textarea v-model="quote" id="quote" name="quote" class="form-control"
        rows="5" @keyup.enter="quoteMe"></textarea>
    </div>
    <button :disabled="quote === ''" class="btn btn-primary btn-block" @click="quoteMe">Quote Me</button>
  </div>
</template>

<script>
import { eventBus } from '../main'
export default {
  data: () => {
    return {
      quote: ""
    }
  },
  methods: {
    quoteMe: function(event) {
      let quote = this.quote;
      eventBus.$emit('quoteWasAdded', quote)
      this.quote = ""
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
