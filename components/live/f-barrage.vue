<template>
	<view class="position-fixed" style="left:0; bottom: 120rpx;">
		<scroll-view scroll-y="true" style="width: 500rpx; height: 300rpx;" scroll-with-animation class="px-3"
			:scroll-into-view="scrollInToView">
			<view :id="'barrage'+item.id" class="flex justify-start align-start rounded p-1 mb-2"
				style="background-color: rgba(255, 255, 255, .125);" v-for="item in list" :key="item.id">
				<text class="font-md text-danger">{{item.name}}: </text>
				<text class="font-md text-white">{{item.barrage}}</text>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		name: 'barrage', //弹幕组件
		data() {
			return {
				list: [],
				scrollInToView: ""
			}
		},
		mounted() {
			// let id = 1
			// setInterval(() => {
			// 	this.list.push({
			// 		id,
			// 		name: '老喷' + id,
			// 		barrage: '火' + id
			// 	})
			// 	// 置于底部
			// 	this.toBottom()
			// 	id++
			// }, 2000)
		},
		methods: {
			sendBarrage(data){
				this.list.push(data)
				this.toBottom()
			},
			toBottom() {
				// 虛擬dom是取不到的
				setTimeout(() => {
					if (this.list.length > 0 && this.list[this.list.length - 1]) {
						this.scrollInToView = 'barrage' + this.list[this.list.length - 1].id
			 	}
				}, 200)

			}
		}
	}
</script>

<style>
</style>
