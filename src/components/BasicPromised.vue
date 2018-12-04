<template>
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
</template>

<script>
import { Promised } from 'vue-promised';

export default {
  components: {
    Promised
  },
  data() {
    return {
      promise: this.delay(),      
    }
  },
  methods: {
    delay() {
      return new Promise(resolve => setTimeout(() => resolve('Resolved!'), 2000));
    }
  }
}
</script>
