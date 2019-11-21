<template>
	<view class="videoList">
		<view class="swiper-box">
			<swiper class="swiper" :vertical="true">
				<swiper-item v-for="item of videos" :key="item.id">
					<view class="swiper-item">
						<video-player :video="item"></video-player>
					</view>
					<view>
						<list-left></list-left>
					</view>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script>
	import videoPlayer from './videoPlayer.vue';
	import listLeft from './listLeft.vue';
	export default {
		props:['list'],
		components:{
			videoPlayer,
			listLeft
		},
		data() {
			return {
				videos:[]
			};
		},
		watch:{
			list(){
				this.videos=this.list
			}
		}
	}
</script>

<style>
.videoList{
	height: 100%;
	width: 100%;
}
.swiper-box{
	height: 100%;
	width: 100%;
}
.swiper{
	height: 100%;
	width: 100%;
}
.swiper-item{
	height: 100%;
	width: 100%;
	z-index: 19;
}
</style>
