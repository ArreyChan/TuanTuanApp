<template>
	<view>
		
		<view class="list_good">
			<view class="goods_item">
				<image src="../../static/picture/10.png"></image>
			
			</view>
			<view class="goods_item">
				<image src="../../static/picture/10.png"></image>
			
			</view>
			<view class="goods_item">
				<image src="../../static/picture/10.png"></image>
		
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

<style>
.isOver{
		width: 100%;
		height: 50px;
		line-height: 50px;
		text-align: center;
		font-size: 25rpx;
	}
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
	} 
</style>
