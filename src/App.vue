<template>
  <div id="app">
    <Search msg="Hello World" v-on:result="result = $event" v-on:error="error = $event"/>
    <h2 id="wynik">{{result}}</h2>
    <h4 id="error">{{error}}</h4>
  </div>
</template>

<script>
import Search from './components/Search.vue'

export default {
  name: 'app',
  components: {
    Search
  },
  data() {
    return {
      error: '',
      result: [],
    }
  }
}
</script>

<style>

</style>
