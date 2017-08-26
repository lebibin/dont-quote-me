<template>
  <div class="container">
    <quote-count :quotes="quotes"></quote-count>
    <quote-form></quote-form>
    <quote-grid :quotes="quotes"></quote-grid>
    <quote-info></quote-info>
  </div>
</template>

<script>
import { eventBus } from './main'
import QuoteCount from './components/QuoteCount.vue'
import QuoteForm from './components/QuoteForm.vue'
import QuoteGrid from './components/QuoteGrid.vue'
import QuoteInfo from './components/QuoteInfo.vue'
export default {
  data: () => {
    return {
      quotes: [
        { id: 1, message: "Never gonna give you up" },
        { id: 2, message: "Never gonna let you down" },
        { id: 3, message: "Never gonna run around and desert you"},
      ]
    }
  },
  components: {
    quoteCount: QuoteCount,
    quoteForm: QuoteForm,
    quoteGrid: QuoteGrid,
    quoteInfo: QuoteInfo
  },
  created() {
    eventBus.$on('quoteWasAdded', (quote) => {
      if (this.quotes.length < 10) {
        this.quotes.push(quote)
      } else {
        alert('You had enough of these damn quotes!');
      }
    })
    eventBus.$on('quoteWasDeleted', (quote) => {
      let indexToDelete = -1;
      for(let i = 0; i < this.quotes.length; i++) {
        let q = this.quotes[i]
        if (quote.id === q.id) {
          indexToDelete = i
          break
        }
      }
      if (indexToDelete > -1) {
        this.quotes.splice(indexToDelete, 1)
      }
    })
  }
}
</script>

<style scoped>
.container {
  margin: 50px auto;
}
</style>
