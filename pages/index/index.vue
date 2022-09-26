<template>
	<view>
	<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" style="width: 750rpx; height: 400rpx;">
		<swiper-item>
			<image src="../../static/demo/banner/1.jpg" style="width: 750rpx; height: 400rpx;"></image>
		</swiper-item>
		<swiper-item>
			<image src="../../static/demo/banner/2.jpg" style="width: 750rpx; height: 400rpx;"></image>
		</swiper-item>
	</swiper>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {
			
		},
		methods: {

		}
	}
</script>

<style>
	
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
	
	.iconfont{
		font-family: iconfont;
		
	}
</style>
