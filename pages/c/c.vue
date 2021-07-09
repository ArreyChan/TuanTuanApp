<template>
	<view>
		<view class="list_good">
			<view class="goods_item">
				<image src="../../static/picture/10.png"></image>
				<view class="price">
					<text>✨ 200</text>
					<text>400</text>
				</view>
				<view class="name">
					元气系列限定产品
				</view>
			</view>
			<view class="goods_item">
				<image src="../../static/picture/10.png"></image>
				<view class="price">
					<text>✨ 200</text>
					<text>400</text>
				</view>
				<view class="name">
					元气系列限定产品
				</view>
			</view>
			<view class="goods_item">
				<image src="../../static/picture/10.png"></image>
				<view class="price">
					<text>✨ 200</text>
					<text>400</text>
				</view>
				<view class="name">
					元气系列限定产品
				</view>
			</view>
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
.list_good{
		padding: 0 15rpx;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		.goods_item{
			background: #FFFFFF;
			width: 330rpx;
			margin: 10rpx 0;
			padding:15rpx ;
			box-sizing: border-box;
			image{
				width: 100%;
				height: 300rpx;
				display: block;
				margin: auto;
			}
		}
			
		.price{
			color: $shop-color ;
			font-size: 30rpx;
			margin: 20rpx 0 5rpx 0;
			font-weight: bold;
			text:nth-child(2){
				color: #C0C0C0;
				font-size: 25rpx;
				margin-left: 17rpx;
				text-decoration: line-through;
			}
		}
		.name{
			font-size: 27rpx;
			line-height: 50rpx;
			padding-bottom: 15rpx;
			padding-top: 10rpx;
			font-weight: bold;
			color: $shop-color;
			
		}
	}
</style>
