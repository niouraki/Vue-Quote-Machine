<template>
  <div id="app" v-bind:style="{ 'background':  myColor}">
    <Quote v-bind:quote="myQuote" />
    <button v-on:click="changeButton">Get a Quote</button>
    <Footer />
  </div>
</template>

<script>
import Quote from './components/Quote'
import Footer from './components/Footer'

export default {
  name: 'app',
  components: {
    Quote,
    Footer
  },
  data() {
    return {
      quotes: [],
      colors: ['#16a085', '#27ae60', '#2c3e50', '#f39c12', '#e74c3c', '#9b59b6', '#FB6964', '#342224', "#472E32", "#BDBB99", "#77B1A9", "#73A857"],
      myColor: "",
      myQuote: []
    }
  },
  methods: {
    getQuote() {
      fetch('https://andruxnet-random-famous-quotes.p.mashape.com/?cat=famous&count=10', {
        headers: { 'X-Mashape-Key': 'nqVAdJTo0dmsh2bZBuvn98LqyL4kp19vye6jsnnrhTntnXEPE1',
                    'Content-Type': 'application/json'}
      })
        .then(response => response.json())
        .then(data => this.quotes = data)
        .catch(error => alert("There has been an error. Please try again later"))
    },
    changeButton() {
      // gets a random color from my colors array
      let color = this.colors[Math.floor(Math.random()*this.colors.length)]
      this.myColor = color

      let quote = this.quotes[Math.floor(Math.random()*this.quotes.length)]
      this.myQuote = quote
    }
  },
  mounted() {
    this.getQuote()
  }
}
</script>

<style>
html, body {
  margin: 0px;
  padding: 0px;
  height: 100%;
}

#app {
  background: purple;
  min-height: 100%;
  text-align: center;
}

button {
  padding: 5px;
  font-size: 18px;
  position: relative;
  top: 70px;
}
</style>
