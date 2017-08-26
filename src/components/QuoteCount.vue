<template>
  <div>
    <h1>{{ title }}</h1>
    <div class="progress">
      <div class="progress-bar"
        role="progressbar"
        :aria-valuenow="countPercentage"
        aria-valuemin="0"
        aria-valuemax="100"
        :style="{ width: (quotes.length * 10) + '%'}">
        <span>{{ quotes.length }}/10</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    quotes: {
      type: Array,
      required: true
    }
  },
  data: () => {
    return {
      title: 'Quotes Added'
    }
  }
}
</script>

<style scoped>
h1 {
  font-size: 26px;
}
.progress {
  height: 20px;
}
</style>
