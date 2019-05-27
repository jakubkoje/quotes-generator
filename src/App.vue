<template>
  <div class="container">
    <Header :number="number"></Header>
    <Search @add-quote="addQuote"></Search>
    <Quotes :quotes="quotes" @remove-quote="removeQuote"></Quotes>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./Header.vue";
import Search from "./Search.vue";
import Quotes from "./Quotes.vue";
import Footer from "./Footer.vue";

export default {
  components: {
    Header,
    Footer,
    Search,
    Quotes
  },
  data() {
    return {
      quotes: [],
      number: 0
    };
  },
  methods: {
    addQuote(value) {
      if (!this.quotes.includes(value)) {
        if (this.number !== 10) {
          this.quotes = [...this.quotes, value];
          this.number++;
        } else {
          alert("You cant have more than 10 quotes!");
        }
      } else {
        alert("You can't have the same quote!");
      }
    },
    removeQuote(value) {
      this.quotes = this.quotes.filter(item => {
        return item !== value;
      });
      this.number--;
    }
  }
};
</script>

<style>
body {
  font-family: Roboto, Arial, Helvetica, sans-serif;
}
</style>
