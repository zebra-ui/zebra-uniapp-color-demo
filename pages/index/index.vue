<template>
	<view class="wrapper">
		<view class="wrapper-top">
			<view class="wrapper-top-title">
				<view class="titleZ" :style="[{color: colors.hex}]">
					Z
				</view>
				<view class="titleE" :style="[{color: colors.hex}]">
					E
				</view>
				<view class="titleB"
					:style="[{backgroundImage: `linear-gradient(90deg, ${colors.hex}, ${colors1.hex})`}]">
					B
				</view>
				<view class="titleR" :style="[{color: colors1.hex}]">
					R
				</view>
				<view class="titleA" :style="[{color: colors1.hex}]">
					A
				</view>
				<view class="line"
					:style="[{backgroundImage: `linear-gradient(90deg, ${colors.hex}, ${colors1.hex})`}]"></view>
				<view class="iconfont icon-yanse" :style="[{color: colors1.hex}]">
				</view>
			</view>
		</view>
		<view class="wrapper-content">
			<view class="wrapper-content-chrome">
				<zebra-color-picker v-model="colors" @input="colorInput"></zebra-color-picker>
			</view>
			<view class="wrapper-content-sketch">
				<zebra-color-picker-sketch v-model="colors1"></zebra-color-picker-sketch>
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				colors: {
					hex: '#7ED321'
				},
				colors1: {
					hex: '#50E3C2'
				},
			}
		},
		created() {
			// uni.loadFontFace({
			// 	global: true,
			// 	family: '851',
			// 	source: 'url("https://cdn.zebraui.com/zebra-ui/851-basic.ttf")',
			// 	success() {
			// 		console.log('success')
			// 	},
			// 	fail() {
			// 		uni.showToast({
			// 			title: '字体加载失败',
			// 			icon: 'none'
			// 		})
			// 	}
			// })
		},
		methods: {
			colorInput(value) {
				// console.log(value)
			}
		}
	}
</script>

<style lang="scss" scoped>
	@import '../../assets/fonts.css';

	.wrapper {
		.wrapper-content {
			margin-top: 30rpx;
			display: flex;
			flex-direction: column;
			align-items: center;

			.wrapper-content-sketch {
				margin-top: 50rpx;
			}
		}

		.wrapper-top {
			margin-top: calc(env(safe-area-inset-bottom) + 80rpx);
			padding: 50rpx;

			.wrapper-top-title {
				font-size: 186rpx;
				font-weight: bold;
				font-family: '851';
				display: flex;
				align-items: center;
				letter-spacing: 20rpx;
				position: relative;

				.line {
					position: absolute;
					bottom: 0;
					left: 0;
					width: 100%;
					height: 20rpx;
					border-radius: 10rpx;
				}

				.icon-yanse {
					font-size: 86rpx;
					font-weight: bold;
					position: absolute;
					right: 0;
					top: 0;
				}

				.titleZ {
					transform: rotate(-20deg);
				}

				.titleE {
					transform: rotate(-20deg);
				}

				.titleB {
					transform: rotate(-20deg);
					-webkit-background-clip: text;
					-webkit-text-fill-color: transparent;
				}

				.titleR {
					transform: rotate(-20deg);
				}

				.titleA {
					transform: rotate(-20deg);
				}
			}
		}
	}
</style>
