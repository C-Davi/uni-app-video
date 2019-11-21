<template>
	<view class="videoPlayer">
		<video class="video"  :controls="false" :loop="true" :src="video.src"  controls></video>
	</view>
</template>

<script>
	export default {
		props:['video'],
		data() {
			return {
				
			};
		}
		
	}
</script>

<style>
.videoPlayer{
	height: 100%;
	width: 100%;
}
.video{
	height: 100%;
	width: 100%;
}
</style>
