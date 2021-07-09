<template>
	<view class="home">
		
		<view class="JJ">
			<text >推荐</text>
			<text class="JJ_1"> 关注</text>
			<text class="JJ_1"> 发现</text>
		</view>
		<swiper indicator-dots circular autoplay="autoplay" indicator-color="#f3e7e9" indicator-active-color="#ff758c">
			<swiper-item>
				<image src="../../static/picture/1.png"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/picture/2.png"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/picture/3.png"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/picture/4.png"></image>
			</swiper-item>
		</swiper>
		<!-- 导航区域 -->
		<view class="nav">
			<view class="nav_item" v-for="(item,index) in navs" :key="index" @click="navItemClick(item.path)" >
				<view :class="item.icon"></view>
				<text>{{item.title}}</text>
			</view>
		</view>
		<!-- 推荐商品 -->
		<view class="good">
			<view class="tit">🎀崽崽推荐🎀</view>
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
	
	export default {
		data() {
			return {
				navs:[
					{
						icon:'iconfont icon-tupian',
						title:'稿图分享',
						path:'/pages/a/a'
					},
					{
						icon:'iconfont icon-shipin',
						title:'你好设计师',
						path:'/pages/b/b'
					},
					{
						icon:'iconfont icon-ziyuan',
						title:'成品超市',
						path:'/pages/c/c'
					},
					{
						icon:'iconfont icon-guanyuwomen',
						title:'在线娃厂',
						path:'/pages/d/d'
					}
				]
				
			}
		},
		onLoad() {

		},
		onPullDownRefresh() {
			setTimeout(()=>{
				uni.stopPullDownRefresh()
			},2000)//延迟刷新2秒
		},
		
		methods: {
			//导航点击处理函数，用来跳转页面使用
			navItemClick(url){
				uni.navigateTo({
					url
				})
			}
		}
	}
</script>

<style lang="scss">
	.home{
		swiper{
			width: 750rpx;
			height: 380rpx;
			image{
				height: 100%;
				width: 100%;
			}
		}
	}
	.JJ{
		.JJ_1{
			color: #333333;
			font-size: 40rpx;
			letter-spacing: 10rpx;
		}
		
		text{
			letter-spacing: 30rpx;
			font-size: 50rpx;
		}
		text-align: left;
		line-height: 100rpx;
		color:$shop-color;
		width: 600rpx;
		height: 100rpx;
		background:#FFFFFF;
		border-radius: 30rpx;
		
	}
	.nav{
		display: flex;
		.nav_item{
			width: 25%;
			text-align: center;
			view{
				width: 150rpx;
				height: 120rpx;
				background:#FFFFFF;
				border-radius: 30rpx;
				margin: 10px auto;
				line-height: 120rpx;
				color:$shop-color;
			
				font-size: 80rpx;
			}
			text{
				color:$shop-color;
			}
			
		.icon-tupian{
			font-size: 60rpx;
		}
		text{
				font-size: 30rpx;
			}
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
