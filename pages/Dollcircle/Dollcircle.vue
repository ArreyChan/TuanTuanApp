<template>
	<view>
		<uni-search-bar @confirm="search" @input="input" ></uni-search-bar>
		<view class="tags">
			<block v-for="(value, index) in data" :key="index">
				<view class="tag" @tap="goList(value)">
					<image class="tag-img" :src="value.icon"></image>
					<text class="tag-text">{{value.type}}</text>
				</view>
			</block>
		</view>
		<view class="good">
			<view class="tit"> 🎁推荐商品</view>
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
	</view>
	
</template>

<script>
	import uniSearchBar from '@/components/uni-search-bar/uni-search-bar.vue'
	export default {
		data() {
			return {
				data: [
					{
						type: '娃衣',
						id: 1,
						icon: '../../static/icon/w.png'
					},
					{
						type: '崽崽',
						id: 2,
						icon: '../../static/icon/z1.png'
					},
					{
						type: '配件',
						id: 3,
						icon: '../../static/icon/p.png'
					},
					{
						type: '好物',
						id: 4,
						icon:'../../static/icon/h.png'
                    }
				]
			}
		},
		methods: {
			goList(value) {
				console.log('南京传媒学院-陈尔睿' + '&id=' + value.id)
			}
		},
		components: {uniSearchBar}
	,
	onPullDownRefresh() {
		setTimeout(()=>{
			uni.stopPullDownRefresh()
		},2000)//延迟刷新2秒
	}
	}
</script>

<style lang="scss">
	page{
		height: 100%;
	} 
	.tags {
		display: flex;
		background: #fff;
		flex: 1;
		width: 710upx;
		margin: 20upx;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: flex-start;
		align-content: flex-start;
	}
	
	view.tag,.tag {
		display: block;
		width: 177.5upx;
		height: 180upx;
		padding: 24upx;
	    line-height: 1;
		box-sizing: border-box;
		text-align: center;
	}
	
	.tag-img {
		border-radius: 60upx;
		width: 120upx;
		height: 120upx;
	}
	
	.tag-text {
		font-size: 28upx;
		color: #555555;
	}
	
	.pic{
		height: 100%;
		.left{
			width: 200rpx;
			height: 100%;
			border-right: 1px solid #eee;
			view{
				height: 60px;
				line-height: 60px;
				color: #333333;
				text-align: center;
				font-size: 30rpx;
				border-top:1px solid #eee;
			}
		}
		.active{
			background: $shop-color;
			color: #FFFFFF;
		}
		
	}
	.good{
		background:#e3eeff ;
		overflow: hidden;
		margin: 20rpx;
		.tit{
			height: 80px;
			line-height:80px;
			color: $shop-color;
			text-align: center;
			letter-spacing: 20px;
			background: #FFFFFF;
			font-size: 40rpx;
			margin: 3rpx 0;
			font-weight: bold;
		}
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
