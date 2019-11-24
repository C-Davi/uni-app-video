<template>
	<view class="content">
		<tab></tab>
		<video-list :list="list"></video-list>
		<first-nav></first-nav>
	</view>
</template>

<script>
	import tab from '../../components/tab.vue'
	import firstNav from '../../components/first-nav.vue'
	import videoList from '../../components/videoList.vue'
	export default {
		components:{
			tab,
			firstNav,
			videoList
		},
		data() {
			return {
				list: []
			}
		},
		onLoad() {
			this.getVideos()
		},
		methods: {
			getVideos(){
				uni.request({
					url:"https://wechat.qtc369.com/static/api/video.json",
					success:(res) => {
						this.list = res.data.list
					}
				})
			}
		}
	}
</script>

<style>
	.content{
		width: 100%;
		height: 100%;
	}
</style>
