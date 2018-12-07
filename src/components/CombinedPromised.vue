<template>
    <Promised :promise="promise">
      <pre slot="combined" slot-scope="{ isPending, isDelayOver, data, error}">        
        <spinner v-if="isPending" />
        <div v-if="data">{{ data }}</div>        
        <div v-if="error">{{ error.message }}</div>
        is delay over: {{ isDelayOver }}
      </pre>      
    </Promised>
</template>

<script>
import { Promised } from 'vue-promised';
import Spinner from './promiseComponents/Spinner'

export default {
  components: {
    Promised,
    Spinner,
  },
  data() {
    return {
      promise: this.response(),      
      delayedPromise: this.delayedResponse(),      
    }
  },
  methods: {
    response() {
      return new Promise( async (resolve) => {                
        const todo = await fetch('https://jsonplaceholder.typicode.com/todos/1');
        resolve(todo.json());        
      });
    },
    delayedResponse() {
      return new Promise( async (resolve) => {                
        const todo = await fetch('https://jsonplaceholder.typicode.com/todos/1');
        setTimeout(() => resolve(todo.json()), 5000);
      });
    }
  }
}
</script>
