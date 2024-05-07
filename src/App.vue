<template>
  <div id="app">
   <SearchBar v-on:termChange="onTermChange"/>
   <VideoList :videos="videos"/>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar.vue';
import VideoList from './components/VideoList.vue';

const API_KEY = process.env.VUE_APP_GOOGLE_API_KEY;

export default {
  // providing name prop helps with debuggging
  name: 'App',
  components: {
    SearchBar,
    VideoList,
  },
  data() {
    return {
      term: '',
      videos: []
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
      }).then(res => {
        this.videos = res.data.items
      })
    }
  }
};
</script>
