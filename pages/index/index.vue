<template>
	<view>
		<!-- 轮播图 -->
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000"
			style="width: 750rpx; height: 400rpx;">
			<swiper-item>
				<image src="../../static/demo/banner/1.jpg" style="width: 750rpx; height: 400rpx;"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/demo/banner/2.jpg" style="width: 750rpx; height: 400rpx;"></image>
			</swiper-item>
		</swiper>
		<!-- 主播列表 -->
		<view class="flex flex-wrap" style="width:100%;">
			<view class="m-1 position-relative" style="width: 355rpx;;height: 355rpx; box-sizing: border-box;"
				v-for="item in 8" :key="item">
				<image src="../../static/demo/1.jpg" class="rounded" mode="aspectFill"
					style="width: 100%; height: 100%;"></image>
				<!-- 左上角提示 -->
				<tips class='position-absolute left font-sm'>
					<text class="iconfont iconbizhongguanli text-warning mr-1"></text>
					<text class="text-white ">0</text>
				</tips>
				<!-- 右上角提示 -->
				<tips class='position-absolute right font-sm'>
					<text class="text-white">人气：</text>
					<text class="text-white">0</text>
				</tips>
				<!--左下角提示:直播間標題 -->
				<view class='position-absolute bottomLeft font  mb-1' style="width:180rpx;">
					<text class="text-white">直播间标题</text>
				</view>
				<!--右下角提示:是否开始 -->
				<tips class='position-absolute bottomRight font-sm flex align-center'>
				<view class="bg-danger rounded-circle" style="width: 20rpx; height: 20rpx;" />
				<text class="pr-1 text-white">已结束</text>
				</tips>
			</view>
		</view>
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

<style lang="scss" scoped>
	// @import "@/common/mixin.scss";
	.left {
		top: 15rpx;
		left: 15rpx;
	}

	.right {
		top: 15rpx;
		right: 15rpx;
	}

	.bottomRight {
		bottom: 15rpx;
		right: 15rpx;
	}

	.bottomLeft {
		bottom: 15rpx;
		left: 15rpx;
	}
</style>
