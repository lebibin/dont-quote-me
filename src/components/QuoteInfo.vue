<template>
  <div class="bg-info">
    <p>
      {{ info  }}
    </p>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      info: "Info: Click on a Quote to delete it!"
    }
  }
}
</script>

<style scoped>
div {
  margin: 25px 0;
  height: 50px;
  border-radius: 5px;
}
p {
  padding: 15px;
  text-align: center;
  color: #337ab7;
}
</style>
