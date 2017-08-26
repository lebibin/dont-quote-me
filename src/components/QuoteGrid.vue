<template>
  <div>
    <quote v-for="(quote, i) in quotes"
      @click.native="deleteQuote(quote)"
      :key="quote.id"
      :quote="quote">
    </quote>
  </div>
</template>

<script>
import { eventBus } from '../main'
import Quote from './Quote.vue'
export default {
  props: {
    quotes: {
      type: Array,
      required: true
    }
  },
  methods: {
    deleteQuote: (quote) => {
      eventBus.$emit('quoteWasDeleted', quote)
    }
  },
  components: {
    quote: Quote
  }
}
</script>

<style scoped>
</style>
