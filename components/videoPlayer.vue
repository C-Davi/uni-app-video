<template>
	<view class="videoPlayer">
		<video id="myVideo" class="video"  :controls="false" :loop="true" :src="video.src" controls @click="click"></video>	
	</view>
</template>

<script>
	export default {
		props:['video'],
		data() {
			return {
				play:false
			};
		},
		onReady(res) {
			this.videoContext = uni.createVideoContext('myVideo',this)
		},
		methods:{
			click(){
				if(!this.play){
					this.player()
				}else{
					this.pause()
				}
			},
			player(){
				if(this.play===false){
					// 从头开始播放
					this.videoContext.seek(0)
					this.videoContext.play()
					this.play = !this.play
				}
			},
			pause(){
				if(this.play===true){
					this.videoContext.pause()
					this.play = !this.play
				}
			},
			reloadPlayer(){
				if(this.play===false){
					this.videoContext.play()
					this.play = !this.play
				}
			}
		}
	}
</script>

<style>
.videoPlayer{
	width: 100%;
	height: 100%;
}
.video{
	width: 100%;
	height: 100%;
}
</style>
