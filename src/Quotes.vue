<template>
  <div class="main">
    <div v-for="(quote) in quotes" :key="quote" class="quote" @click="removeQuote(quote)">
      <p>{{quote}}</p>
    </div>
    {{quote}}
  </div>
</template>

<script>
export default {
  name: "Quotes",
  props: {
    quotes: Array
  },
  methods: {
    removeQuote(quote) {
      this.$emit("remove-quote", quote);
    }
  }
};
</script>

<style scoped>
.main {
  display: grid;

  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  grid-template-rows: auto;
  grid-auto-flow: row;
  width: 75%;
  margin: auto;
}
.quote {
  font-family: Arizonia;
  border: 1px black solid;
  cursor: pointer;
  font-size: 2rem;
  margin: 1rem;
  word-wrap: break-word;
  padding: 1rem 2rem;
}

.quote:hover {
  background-color: #ffe2e2;
}

p {
  margin: 0;
}
</style>
