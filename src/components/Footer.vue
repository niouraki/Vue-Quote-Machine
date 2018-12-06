<template>
  <footer class="footer">
    <p>Made with Vue.js <i class="fas fa-spin fa-coffee"></i> and <i class="fas fa-spin fa-heart"></i></p>
    <span style="z-index:50;font-size:0.9em;">
    <a href="https://rapidapi.com/andruxnet/api/random-famous-quotes" target="_blank" title="Powered by Random Famous Quotes from RapidAPI" style="margin-left: 4px; vertical-align: middle;">RapidAPI</a>
</span>
</footer>
</template>

<script>
export default {
  name: 'Quote',
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.footer {
  height: auto;
  position: absolute;
  bottom: 0;
  background: white;
  width: 100%;
}
</style>
