<template>
  <div>
    <h1>
      {{ title }}
    </h1>
    <p>
      <small style="float:left" @click="increaseLimit">
        buy more quotes...
      </small>
      <span style="float:right">{{ quotes.length }} / {{ quoteLimit }}</span>
    </p> 
    <br>
    <div class="progress">
      <div class="progress-bar"
        role="progressbar"
        :aria-valuenow="countPercentage"
        aria-valuemin="0"
        aria-valuemax="100"
        :style="{ width: ((quotes.length / quoteLimit) * 100) + '%'}">
      </div>
    </div>
  </div>
</template>

<script>
import { eventBus } from '../main'
export default {
  props: {
    quoteLimit: {
      type: Number,
      required: true
    },
    quotes: {
      type: Array,
      required: true
    }
  },
  methods: {
    increaseLimit: () => {
      eventBus.$emit('increaseQuoteLimit')
    }
  },
  data: () => {
    return {
      title: 'Quotes'
    }
  }
}
</script>

<style scoped>
h1 {
  font-size: 26px;
  text-align: center;
}
.progress {
  height: 20px;
}
small {
  cursor: pointer;
}
</style>
