<template>
  <div id="app">
   <SearchBar />
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue';
export default {
  // providing name prop helps with debuggging
  name: 'App',
  components: {
    SearchBar
  }
};
</script>
