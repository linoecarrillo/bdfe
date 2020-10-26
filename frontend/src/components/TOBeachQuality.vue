<template>
  <div class="tobq">
    {{ bq }}
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'TOBeachQuality',
  data () { return {
    bq: null,
  }},
  mounted () {
    axios
      .get('http://localhost:3000/api/v1/report')
      .then(response => {this.bq = response.data})
      .catch(error => {window.alert(`The API returned an error: ${error}`)})
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
