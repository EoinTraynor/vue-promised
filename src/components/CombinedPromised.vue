<template>
    <Promised :promise="promise">
      <pre slot="combined" slot-scope="{ isPending, isDelayOver, data, error}">
        pending: {{ isPending }}
        is delay over: {{ isDelayOver }}
        data: {{ data }}
        error: {{ error && error.message }}
      </pre>      
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
