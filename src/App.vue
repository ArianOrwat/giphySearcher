<template>
  <div id="app">
    <Search msg="Hello World" v-on:result="result = $event" v-on:error="error = $event"/>
    <div v-for="item in result" :key="item.title" class="image">
      <img :src="item.images.downsized.url" :alt="item.title">
    </div>
    <h4 id="error">{{error}}</h4>
  </div>
</template>
<script>
import Search from './components/Search.vue';
// import Result from './components/Result.vue';

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
