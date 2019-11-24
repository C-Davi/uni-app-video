<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
			uni.hideTabBar()
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	html,body{
		width: 100%;
		height: 100%;
	}
	@font-face {font-family: "iconfont";
	  src: url('data:application/x-font-woff2;charset=utf-8;base64,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') format('woff2')}
	
	.iconfont {
	  font-family: "iconfont" !important;
	  font-size: 16px;
	  font-style: normal;
	  -webkit-font-smoothing: antialiased;
	  -moz-osx-font-smoothing: grayscale;
	}
	
	.iconpen:before {
	  content: "\e608";
	}
	
	.iconaixin:before {
	  content: "\e640";
	}
	
	.iconchahao:before {
	  content: "\e617";
	}
	
	.iconshare:before {
	  content: "\e67c";
	}
	
	.iconsousuo:before {
	  content: "\e615";
	}
	
	.icondelete:before {
	  content: "\e635";
	}
	
	.iconbofang:before {
	  content: "\e610";
	}
	
	.iconfanhui:before {
	  content: "\e677";
	}
	
	.iconicon-test:before {
	  content: "\e62a";
	}
	
	.iconxiangji:before {
	  content: "\e60e";
	}
	
	.iconweb-icon-:before {
	  content: "\e6dc";
	}
	
	.iconjiahao:before {
	  content: "\e607";
	}
	
	.iconfenxiang:before {
	  content: "\e626";
	}
	
	.icondingwei:before {
	  content: "\e61c";
	}
	
	.icontubiaozhizuo-:before {
	  content: "\e60f";
	}
	
	.iconchangyongicon-:before {
	  content: "\e612";
	}
</style>
