<template>
  <div class="container">
    <quote-count :quotes="quotes"></quote-count>
    <quote-form></quote-form>
    <quote-grid :quotes="quotes"></quote-grid>
    <quote-info></quote-info>
  </div>
</template>

<script>
import QuoteCount from './components/QuoteCount.vue'
import QuoteForm from './components/QuoteForm.vue'
import QuoteGrid from './components/QuoteGrid.vue'
import QuoteInfo from './components/QuoteInfo.vue'
export default {
  data: () => {
    return {
      quotes: [
        "Never gonna give you up",
        "Never gonna let you down",
        "Never gonna run around and desert you",
      ]
    }
  },
  components: {
    quoteCount: QuoteCount,
    quoteForm: QuoteForm,
    quoteGrid: QuoteGrid,
    quoteInfo: QuoteInfo
  }
}
</script>
<style scoped>
.container {
  margin: 50px auto;
}
</style>
