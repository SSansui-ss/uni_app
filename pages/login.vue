<template>
	<view>
		<view class="box">
			<image src="../static/image/logo2.png" mode=""></image>
			<view class="center">
				<input type="text" v-model="telphone" placeholder="请输入手机" />
				<input type="password" v-model="password" placeholder="请输入密码" />
			</view>
			<view class="BTN">
				<text @click="Go">登录</text>
			</view>
			<view class="BTM">
				<text>忘记密码</text>
				<text>注册账户</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				telphone: '18888888888',
				password: '123456'
			}
		},
		methods: {
			Go() {
				uni.request({
					url: 'http://api.intewl.cn/api/index/login',
					method: 'POST',
					data: {
						telphone: this.telphone,
						password: this.password
					},
					success: (res) => {
						console.log(res)
						if (res.data.code == 0) {
							uni.showToast({
								title: res.data.msg,
								icon: 'none'
							})
						} else {
							uni.setStorageSync('token',res.data.data.token)
							uni.switchTab({
								url:'user/user'
							})
							uni.showToast({
								title: res.data.msg,
								icon: 'none'
							})
						}
					}
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
		height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;

		image {
			text-align: center;
			width: 280rpx;
			height: 150rpx;
			margin-top: 25%;
		}

		.center {
			width: 100%;
			padding: 0 100rpx;
			margin-top: 200rpx;

			input {
				width: 100%;
				border-bottom: 1rpx solid #eeeeee;
				padding: 10rpx;
				margin-bottom: 50rpx;
			}

		}

		.BTN {
			width: 72%;
			height: 90rpx;
			text-align: center;
			background-color: #23BAEF;

			text {
				color: #FFFFFF;
				line-height: 90rpx;
			}
		}

		.BTM {
			margin-top: 30rpx;
			font-size: 14rpx;
			font-weight: bold;

			text:nth-of-type(1) {
				padding: 0 25rpx;
				border-right: 1rpx solid #000000;
			}

			text:nth-of-type(2) {
				padding: 0 25rpx;
				color: #23BAEF;
			}
		}
	}
</style>
