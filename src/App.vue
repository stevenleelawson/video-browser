<template>
  <div id="app">
   <SearchBar v-on:termChange="onTermChange"/>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue';
const API_KEY = 'AIzaSyDjn1izn3Td1YVuyuCwX13JwNn8e6cPvoE';

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
    }
  }
};
</script>
