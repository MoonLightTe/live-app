<template>
	<view  style="height: 500rpx;">
		<scroll-view scroll-y="true" style="width: 520rpx; height: 500rpx;" >
			<view class="flex align-center px-3">
				<view class="rounded-circle flex justify-between align-center" style="width: 325rpx;background-image:linear-gradient(to right,#bcabb1,#65aaf0); height: 80rpx;">
						<!--送禮物的人的頭像 -->
					<view class="p" >
						<image src="../../static/logo.png" style="width: 70rpx; height: 70rpx;" class=" rounded-circle"></image>
					</view>
					<view class="flex-1">
						<text class="text-white font">昵稱</text>
						<text class="text-white font">送蛋糕</text>
					</view>
					<!-- 禮物的圖片 -->
					<view class="p" >
						<image src="../../static/logo.png" style="width: 70rpx; height: 70rpx;" class=" rounded-circle"></image>
					</view>
				</view>
				<view class="flex ml-2 align-center" style="height: 80rpx;">
				<text class="text-warning">X</text>
				<text class="text-warning ml-1">10</text>
			</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
</script>

<style>
</style>