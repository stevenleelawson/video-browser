<template>
	<div>
		<ul class="video-list">
			<VideoListItem
				v-for="video in videos"
				:video="video"
				:key="video.etag"
			></VideoListItem>
		</ul>
	</div>
</template>

<script>
import VideoListItem from './VideoListItem.vue';
export default {
	name: 'VideoList',
	props: [ 'videos'],
	components: {
		VideoListItem,
	}
}
</script>

<style>

</style>