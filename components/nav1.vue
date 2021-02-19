<template>
	<view class="box">
		<view v-for="(item,index) in list" class="nav1" :key="index" @click="Path(item.path)">
			<view>
				<image :src="item.imgSrc"></image>
			</view>
			<view><text>{{item.title}}</text></view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
						title: '待付款',
						imgSrc: require("static/image/member-icon1.png"),
						path: '/pages/user/one'
					},
					{
						title: '待收货',
						imgSrc: require("static/image/member-icon2.png"),
						path: '/pages/user/er'
					},
					{
						title: '待评论',
						imgSrc: require("static/image/member-icon3.png"),
						path: '/pages/user/san'
					},
					{
						title: '全部订单',
						imgSrc: require("static/image/member-icon4.png"),
						path: '/pages/user/si'
					},
				],
			};
		},
		methods: {
			Path(index) {
				console.log(index)
				uni.navigateTo({
					url: `${index}`
				})
			}
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
		display: flex;
		justify-content: space-between;
	}

	.nav1 {
		padding: 20rpx 0;
		width: 25%;
		text-align: center;

		image {
			width: 60rpx;
			height: 50rpx;
		}
	}
</style>
