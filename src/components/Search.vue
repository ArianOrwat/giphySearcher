<template>
  <div class="search">
    <div>{{msg}}</div>
    <input id="search" type="text" @input="search"/>
  </div>
</template>

<script>

import axios from 'axios';
import debounce from 'lodash.debounce';

const API = 'https://api.giphy.com/v1/gifs/search?api_key=fHRCXpCm0g0bZekk3MnhMQEpXm8vEmNd';

export default {
  name: 'Search',
  props: {
    msg: String,
  },
  data() {
    return {
      input: '',
    }
  },
  methods: {
    search: debounce(function () {
      this.input = document.querySelector('#search').value;
      axios.get(`${API}&q=${this.input}&limit=15&offset=0&rating=G&lang=en`)
        .then(result => this.$emit('result', result.data.data))
        .catch(err => this.error = this.$emit('error', err))
    }, 500),
  },
}
</script>

<style lang="sass" scoped>

</style>
