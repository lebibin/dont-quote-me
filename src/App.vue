<template>
  <div class="container">
    <quote-count></quote-count>
    <quote-form></quote-form>
    <quote-info></quote-info>
  </div>
</template>

<script>
import QuoteCount from './components/QuoteCount.vue'
import QuoteForm from './components/QuoteForm.vue'
import QuoteInfo from './components/QuoteInfo.vue'
export default {
  components: {
    quoteCount: QuoteCount,
    quoteForm: QuoteForm,
    quoteInfo: QuoteInfo
  }
}
</script>
<style scoped>
.container {
  margin: 50px auto;
}
</style>
