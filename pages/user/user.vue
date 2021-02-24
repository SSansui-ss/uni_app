<template>
	<view>
		<image src="/static/image/member-top.png" class="back"></image>
		<view class="top_add">
			<view class="top_icon">
				<view class="iconfont icon-RectangleCopy1 ICon_f"></view>
				<view class="iconfont icon-RectangleCopy ICon_f"></view>
			</view>
		</view>
		<view class="top_arr">
			<view>
				<image v-if="isAdd" src="../../static/static/image/empty-tx.png" mode=""></image>
			</view>
			<view v-if="isAdd">
				<text>英特网络</text>
				<text>18888888888</text>
			</view>
			<view class="Log" v-if="isAdd == 0">
				<text class="TEXT" @click="GoLogin">登陆/注册</text>
			</view>
			<view>
				<image src="../../static/static/image/ewm.png" mode=""></image>
			</view>
		</view>
		<nav1></nav1>
		<view class="Cl"></view>
		<nav2></nav2>
		<button size="default" @click="Esc" v-if="isAdd == 1">退出登陆</button>
	</view>
</template>

<script>
	import nav1 from '../../components/nav1.vue'
	import nav2 from '../../components/nav2.vue'
	export default {
		data() {
			return {
				isAdd: 1
			}
		},
		components: {
			nav1,
			nav2
		},
		computed: {},
		onShow() {
			this.IfIsAdd()
		},
		methods: {
			Esc() {
				this.isAdd = 0
				uni.removeStorageSync('token')
				uni.showToast({
					title: '退出成功',
					icon: 'none',
				})
			},
			GoLogin() {
				uni.navigateTo({
					url: '/pages/login'
				})
			},
			IfIsAdd(){
				let token = uni.getStorageSync("token")
				console.log(token)
				if (token == '') {
					this.isAdd = 0
				}else{
					this.isAdd = 1
				}
			}
		},
		
	}
</script>

<style lang="scss">
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}

	.back {
		width: 100%;
		height: 350rpx;
		position: relative;
	}

	.top_add {
		position: absolute;
		top: 20rpx;
		right: 30rpx;

		.top_icon {
			display: flex;
		}

		.ICon_f {
			font-size: 50rpx;
			color: #ffffff;
		}

		.ICon_f:nth-of-type(1) {
			margin-right: 25rpx;
		}
	}

	button {
		width: 94%;
		text-align: center;
		margin-top: 20rpx;
	}

	.Cl {
		width: 100%;
		height: 15rpx;
		background-color: #F5F5F5;
	}

	.top_arr {
		position: absolute;
		top: 160rpx;
		width: 100%;
		display: flex;
		text-align: left;
		padding: 30rpx;
		align-items: center;
		justify-content: space-between;

		view:nth-of-type(1) {
			width: 10%;

			image {
				width: 80rpx;
				height: 80rpx;
				border-radius: 50%;
			}
		}

		view:nth-of-type(2) {
			padding-left: 25rpx;
			color: #fff;
			flex: 1;
			display: flex;
			flex-direction: column;
		}

		view:nth-of-type(3) {
			margin-right: 25rpx;
			width: 10%;

			image {
				width: 40rpx;
				height: 40rpx;
			}
		}
	}

	.TEXT {
		width: 150rpx;
		border: 1rpx solid #FFFFFF;
		padding: 5rpx 0 5rpx 6rpx;
	}
</style>
