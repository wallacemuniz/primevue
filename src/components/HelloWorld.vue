<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
  const axios = require('axios');

  export default {

    name: 'HelloWorld',

    created() {

      axios.get('http://localhost:8080/est002')
      .then(function (response) {
        // handle success
        console.log('sucesso --->>> ' + response);
      })
      .catch(function (error) {
        // handle error
        console.log('erro --->>> ' + error);
      })
      .then(function () {
        // always executed
      });

    }

  }
</script>