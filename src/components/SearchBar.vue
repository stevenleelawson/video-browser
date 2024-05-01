<template>
	<div>
		<!-- @ === v-on: -->
		<input @input="onInput"/>
	</div>
</template>

<script>
export default {
	name: 'SearchBar',
	methods: {
    onInput: function(e) {
	// 			('nameOftheEventtobeEmitted', value)
      this.$emit('termChange', e.target.value)
    }
  }
};
</script>