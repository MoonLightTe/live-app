<template>
	<list style="width: 520rpx; height: 500rpx;" :show-scrollbar='false' :bounce='false'>
		<!-- 注意事项: 不能使用 index 作为 key 的唯一标识 -->
		<!-- 设置进入动画和离场动画insert-animation delete-animation -->
		<cell v-for="(item,index) in gifts" :key="index" class="flex align-center px-3 pt-3" insert-animation='default'
			delete-animation='default' :ref="'item'+ index">
			<view class="rounded-circle flex justify-between align-center"
				style="width: 325rpx;background-image:linear-gradient(to right,#bcabb1,#65aaf0); height: 80rpx;">
				<!--送禮物的人的頭像 -->
				<view class="p">
					<image :src="item.avatar || DefaultAvatar " style="width: 70rpx; height: 70rpx;"
						class=" rounded-circle"></image>
				</view>
				<view class="flex-1">
					<text class="text-white font">{{item.username}}</text>
					<text class="text-white font">送{{item.gift_name}}</text>
				</view>
				<!-- 禮物的圖片 -->
				<view class="p">
					<image src="item.gift_image" style="width: 70rpx; height: 70rpx;" class=" rounded-circle"></image>
				</view>
			</view>
			<view class="flex ml-2 align-center" style="height: 80rpx;">
				<text class="text-warning">X</text>
				<text class="text-warning ml-1">{{item.num}}</text>
			</view>


		</cell>
	</list>

</template>

<script>
	const dom = weex.requireModule('dom')
	export default {
		data() {
			return {
				// 礼物列表
				gifts: [],
				// 默认头像
				DefaultAvatar: "../../static/logo.png",
				// 定时器id
				timer: ''
			}
		},
		// 组件中是不存在onload的 我们可以使用 created
		created() {
			setInterval(() => {
				this.gifts.push({
					username: '小智',
					avatar: "../../static/logo.png",
					gift_name: "小火龙",
					gift_image: '../../static/gift/3.png',
					num: 1,
				})
				this.toBottom()
				this.autoHide()
			}, 3000)
		},
		methods: {
			// 我们需要解决一个问题 ，就是礼物不会滚动的问题 weex 有一个dom模块
			// 1.给每一个cell组件动态绑定一个ref 在使用weex的一个方法来实现
			// 2.操作dom一定需要在nextTick这个钩子函数中来进行
			// 虚拟dom的时候我们是读不到的
			toBottom() {
				this.$nextTick(() => {
					let index = this.gifts.length - 1;
					let ref = 'item' + index
					if (this.$refs[ref]) {
						dom.scrollToElement(this.$refs[ref][0], {})
					}
				})

			},
			// 自动消失1
			autoHide() {
				// 设置几秒自动移除礼物效果
				// 需要有礼物才启动
				if (this.gifts.length) {
					this.timer = setInterval(() => {
						this.gifts.splice(0, 1)
					}, 5000)
				}
			}
		},
		watch:{
			timer(newId,oldId){
				if(oldId !== ''){
					setTimeout(()=>{
						clearInterval(oldId)
					},5000)
				}
			}
		}
	}
</script>

<style>
</style>
