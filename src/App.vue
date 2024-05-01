<template>
  <div id="app">
   <SearchBar v-on:termChange="onTermChange"/>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue';
import axios from 'axios';

const API_KEY = process.env.VUE_APP_GOOGLE_API_KEY;

export default {
  // providing name prop helps with debuggging
  name: 'App',
  components: {
    SearchBar
  },
  data() {
    return {
      term: ''
    }
  },
  methods: {
    // SAME AS onTermChange: function() {}
    onTermChange(searchTerm) {
      this.term = searchTerm;
      
      axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          key: API_KEY,
          type: 'video',
          part: 'snippet',
          q: this.term
        }
      }).then(res => console.log(res))
    }
  }
};
</script>
