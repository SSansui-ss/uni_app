<template>
	<view class="box">
		<view v-for="(item,index) in list" class="nav2" :key="index">
			<view>
				<image :src="item.imgSrc"></image>
			</view>
			<view><text>{{item.title}}</text></view>
			<view>
				<image src="../static/image/more.png"></image>
			</view>



		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
						title: '收货地址',
						imgSrc: require("static/image/member-menu1.png"),
						path: '/pages/myRecommend/myRecommend'
					},
					{
						title: '在线客服',
						imgSrc: require("static/image/member-menu2.png"),
						path: '/pages/promote/promote'
					},
					{
						title: '邀请有礼',
						imgSrc: require("static/image/member-menu3.png"),
						path: '/pages/capital/capital'
					},
					{
						title: '关于我们',
						imgSrc: require("static/image/member-menu4.png"),
						path: '/pages/setting/setting'
					},
				],
			};
		}
	}
</script>

<style lang="scss">
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}

	.box {
		width: 100%;
		padding: 0 20rpx;
	}

	.nav2:nth-of-type(1) {
		border-top: 0px;
	}

	.nav2 {
		width: 100%;
		padding: 20rpx 0;
		border-top: 1rpx solid #E6E6E6;
		display: flex;
		justify-content: space-between;

		view:nth-of-type(1) {
			width: 10%;

			image {
				width: 30rpx;
				height: 30rpx;
			}
		}

		view:nth-of-type(2) {
			flex: 1;

			text {
				width: 85%;
				padding: 0 15rpx;
			}
		}
		view:nth-of-type(3) {
			width: 10%;
			image {
				width: 30rpx;
				height: 30rpx;
			}
		}
	}
</style>
