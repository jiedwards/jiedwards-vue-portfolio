<template>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/css/materialize.min.css"/>
  <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div id="App">
    <Navbar />
    <Portfolio />
    <PortfolioProjectContainer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import PortfolioProjectContainer from './components/PortfolioProjectContainer.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    PortfolioProjectContainer
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
