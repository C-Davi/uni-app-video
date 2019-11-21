<template>
	<view class="firstNav">
		<view class="iconfont iconsousuo icon"></view>
		<view class="middle">
			<view class="text">推荐</view>
			<view class="text">同城</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style>
.firstNav{
	width: 100%;
	position: fixed;
	top: 25px;
	left: 0;
	height: 35px;
	line-height: 35px;
	margin: 0 auto;
	z-index: 20;
}
.icon{
	position: absolute;
	top: 0;
	left: 0;
	color: #FFFFFF;
	width: 20%;
	text-align: center;
	font-size: 20px;
}
.middle{
	text-align: center;
}
.text{
	display: inline;
	color: #FFFFFF;
	margin: 0 10px;
}
</style>
