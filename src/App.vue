<template>
  <div id="app">
    <Navbar />
   <h1>{{ title }}</h1>
  </div>
</template>

<script>

import Navbar from './Navbar'

export default {
  name: 'app',
  components: {
    NavBar
  },
  data () {
    return {
      title: 'My first vue app by brent'
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  color: aqua;
  font-weight: bold;
}


</style>
