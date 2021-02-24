<template>
	<view>
		我是购物车

		<uni-grid :column="4">
			<uni-grid-item>
				<text class="text">文本</text>
			</uni-grid-item>
			<uni-grid-item>
				<text class="text">文本</text>
			</uni-grid-item>
			<uni-grid-item>
				<text class="text">文本</text>
			</uni-grid-item>
			<uni-grid-item>
				<text class="text">文本</text>
			</uni-grid-item>
			<uni-grid-item>
				<text class="text">文本</text>
			</uni-grid-item>
			<uni-grid-item>
				<text class="text">文本</text>
			</uni-grid-item>
			<uni-grid-item>
				<text class="text">文本</text>
			</uni-grid-item>
			<uni-grid-item>
				<text class="text">文本</text>
			</uni-grid-item>
		</uni-grid>
	</view>
</template>

<script>
	import {
		uniGrid,
		uniGridItem
	} from '@dcloudio/uni-ui'
	export default {
		data() {
			return {

			}
		},
		components: {

			uniGrid,
			uniGridItem
		},
		methods: {

		}
	}
</script>

<style>

</style>
