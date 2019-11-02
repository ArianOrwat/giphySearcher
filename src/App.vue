<template>
  <div id="app">
    <Search msg="Hello World" v-on:result="result = $event" v-on:error="error = $event"/>
    <div class="grid">
      <Result v-for="item in result" :key="item.title + ' ' + item.import_datetime" :src="item.images.fixed_width.url" :alt="item.title"/>
    </div>
    <h4 id="error">{{error}}</h4>
  </div>
</template>
<script>
import Search from './components/Search.vue';
import Result from './components/Result.vue';

export default {
  name: 'app',
  components: {
    Search,
    Result
  },
  data() {
    return {
      error: '',
      result: [],
    }
  }
}
</script>

<style lang="scss">
  .grid {
    display: grid;
    grid-template-columns: auto auto auto;
  }

  @media only screen and (max-width: 1200px) {
    .grid {
      grid-template-columns: auto auto;
    }
  }

  @media only screen and (max-width: 600px) {
    .grid {
      grid-template-columns: auto;
    }
  }
</style>
