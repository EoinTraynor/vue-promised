<template>
  <div id="app">
    <Promised :promise="promise">
      <!--
        Use the "pending" slot for loading content
      -->
      <h1 slot="pending">Loading</h1>
      <!-- The default scoped slots will be used as the result -->
      <h1 slot-scope="data">Success! {{ data }}</h1>
      <!-- The "rejected" scoped slot will be used if there is an error -->
      <h1 slot="rejected" slot-scope="error">Error: {{ error.message }}</h1>
    </Promised>
  </div>
</template>

<script>
import { Promised } from 'vue-promised';

export default {
  name: 'app',  
  data() {
    return {
      promise: this.delay(),      
    }
  },
  components: {
    Promised
  },
  methods: {
    delay() {
      return new Promise(resolve => setTimeout(() => resolve('boo'), 2000));
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
</style>
