<template>
	<view class="tab">
		<view class="tab-box">首页</view>
		<view class="tab-box">关注</view>
		<view class="tab-box">
			<view class="iconfont iconadd icon-box"></view>
		</view>
		<view class="tab-box">消息</view>
		<view class="tab-box">我</view>
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
.tab{
	height: 50px;
	width: 100%;
	position: fixed;
	bottom: 0;
	left: 0;
}
.tab-box{
	float: left;
	width: 20%;
	color: #FFFFFF;
	text-align: center;
	height: 50px;
	line-height: 50px;
	font-size: 20px;
}
.icon-box{
	width: 60%;
	height: 30px;
	background: #FFFFFF;
	color: #000000;
	margin: 10px auto;
	line-height: 30px;
	border-radius: 5px;
	font-size: 15px;
}
</style>
