<template>
  <div id="app">
    <basic-promised />
    <combined-promised />
  </div>
</template>

<script>
import BasicPromised from './components/BasicPromised';
import CombinedPromised from './components/CombinedPromised';

export default {
  name: 'app',  
  components: {
    BasicPromised,
    CombinedPromised,
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
