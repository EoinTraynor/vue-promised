<template>
  <div id="app">
    <basic-promised />
  </div>
</template>

<script>
import BasicPromised from './components/BasicPromised';

export default {
  name: 'app',  
  components: {
    BasicPromised,
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
</style>
