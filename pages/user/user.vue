<template>
	<view>
		<image src="/static/image/member-top.png" class="back"></image>
		<view class="top_add">
			<view>
				<image src="../../static/static/image/ewm.png" mode=""></image>
				<image src="../../static/static/image/ewm.png" mode=""></image>
			</view>
		</view>
		<view class="top_arr">
			<view>
				<image src="../../static/static/image/empty-tx.png" mode=""></image>
			</view>
			<view>
				<text>英特网络</text>
				<text>18888888888</text>
			</view>
			<view>
				<image src="../../static/static/image/ewm.png" mode=""></image>
			</view>
		</view>
		<nav1></nav1>
		<view class="Cl"></view>
		<nav2></nav2>
		<button size="default">退出登陆</button>
	</view>
</template>

<script>
	import nav1 from '../../components/nav1.vue'
	import nav2 from '../../components/nav2.vue'
	export default {
		data() {
			return {}
		},
		components: {
			nav1,
			nav2
		},
		methods: {

		}
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

		image {
			width: 30rpx;
			height: 30rpx;
		}

		image:nth-of-type(1) {
			margin-right: 50rpx;
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
</style>
