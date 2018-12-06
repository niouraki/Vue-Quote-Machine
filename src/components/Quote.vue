<template>
  <div class="box">
    <div>
    <p>{{ quote.quote }}</p>
    <p>{{ quote.author }}</p>
  </div>
  </div>
</template>

<script>
export default {
  name: 'Quote',
  props: ['quote'],
  data() {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.box {
  position: relative;
  top: 50px;
  border: 2px solid black;
  width: 50%;
  height: 150px;
  margin: 0 auto;
  padding: 50px;
  background: white;
  text-align: center;
}

p {
  font-size: 20px;
}
</style>
