<template>
  <div>
    <div class="quote" v-for="quote in quotes">
      <p>{{ quote  }}</p>
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
  }
}
</script>

<style scoped>
.quote {
  display: inline-block;
  margin: 15px;
  border: 1px #eee solid;
  border-radius: 5px;
  width: 30%;
}

p {
  margin: 0;
  padding: 15px;
  text-align: center;
  font-family: "Comic Sans MS", cursive, sans-serif;
  font-size: 24px;
}

.quote:hover {
  background-color: #d9534f;
  color: #fff;
  cursor: pointer;
}
</style>
