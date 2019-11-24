<template>
	<view class="videoList">
		<view class="video">
			<view class="swiper-box">
				<swiper class="swiper" :vertical="true" @change="change" @touchstart="touchStart" @touchend="touchEnd">
					<swiper-item v-for="item of videos" :key="item.id">
						<view class="swiper-item">
							<video-player :video="item" ref="player"></video-player>
						</view>
						<view class="left-box">
							<list-left></list-left>
						</view>
						<view class="right-box">
							<list-right></list-right>
						</view>
					</swiper-item>
				</swiper>
			</view>
		</view>
	</view>
</template>

<script>
	import videoPlayer from './videoPlayer.vue'
	import listLeft from './listLeft.vue'
	import listRight from './listRight.vue'
	let time = null
	export default {
		props:[
			'list'
		],
		components:{
			videoPlayer,
			listLeft,
			listRight
		},
		data() {
			return {
				videos:[],
				pageStartY:0,
				pageEndY:0,
				page:0
			};
		},
		watch:{
			list(){
				console.log(this.list)
				this.videos = this.list
			}
		},
		methods:{
			// 监听上下滑动
			change(res){
				// 定时器解决触摸开始结束间隔问题
				clearTimeout(time)
				this.page= res.detail.current
				time=setTimeout(()=>{
					if(this.pageStartY>this.pageEndY){
						// 上滑动
						this.$refs.player[this.page].player()
						this.$refs.player[this.page-1].pause()
						this.pageStartY=0
						this.pageEndY=0
					}else{
						// 下滑动
						this.$refs.player[this.page].player()
						this.$refs.player[this.page+1].pause()
						this.pageStartY=0
						this.pageEndY=0
					}
				},1)
			},
			// 触摸开始
			touchStart(res){
				this.pageStartY=res.changedTouches[0].pageY
			},
			// 触摸结束
			touchEnd(res){
				this.pageStartY=res.changedTouches[0].pageY
			}
		}
	}
</script>

<style>
.videoList{
	width: 100%;
	height: 100%;
}
.video{
	width: 100%;
	height: 100%;
}
.swiper-box{
	width: 100%;
	height: 100%;
}
.swiper{
	width: 100%;
	height: 100%;
}
.swiper-item{
	width: 100%;
	height: 100%;
	z-index: 19;
}
.left-box{
	z-index: 20;
	position: absolute;
	bottom: 50px;
	left: 10px;
}
.right-box{
	z-index: 20;
	position: absolute;
	bottom: 50px;
	right: 10px;
}
</style>
