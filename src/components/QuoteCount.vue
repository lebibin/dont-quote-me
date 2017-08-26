<template>
  <div>
    <h1>{{ title }}</h1>
    <div class="progress">
      <div class="progress-bar" role="progressbar" aria-valuenow="0"
        aria-valuemin="0" aria-valuemax="100" style="width:0%">
        <span>0/10</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
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
