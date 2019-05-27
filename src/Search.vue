<template>
  <div>
    <p>Quote</p>
    <textarea name="search" id="search" v-model="quote" placeholder="Quote..."></textarea>
    <button @click="addQuote">Add Quote</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quote: ""
    };
  },
  methods: {
    addQuote() {
      if (this.quote.trim() !== "") {
        this.$emit("add-quote", this.quote);
        this.quote = "";
      } else {
        alert("You can't have an empty quote.");
      }
    }
  }
};
</script>

<style scoped>
div {
  margin: auto;
  margin-top: 2rem;
  width: 50%;
  text-align: center;
}
p {
  font-weight: 600;
  text-align: left;
}
textarea {
  width: 100%;
  resize: none;
  outline: none;
  height: 3rem;
}

button {
  text-align: center;
  margin-top: 1rem;
}
</style>
