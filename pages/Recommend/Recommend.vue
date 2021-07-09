<template>
	<view class="index">
		<view class="tags">
			<block v-for="(value, index) in data" :key="index">
				<view class="tag" @tap="goList(value)">
					<image class="tag-img" :src="value.icon"></image>
					<text class="tag-text">{{value.type}}</text>
				</view>
			</block>
		</view>
		<view class="nav">
			<image  class="na" src="../../static/icon/5.png"></image>
			<view class="nav_item" v-for="(item,index) in navs" :key="index" @click="navItemClick(item.path)" >
				<view >重要通知</view>
				<text>{{item.title}}</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				data: [
					{
						type: '收到的赞',
						id: 1,
						icon: '../../static/icon/1.png'
					},
					{
						type: '评论和@',
						id: 2,
						icon: '../../static/icon/2.png'
					},
					{
						type: '私信',
						id: 3,
						icon: '../../static/icon/3.png'
					},
					{
						type: '新的好友',
						id: 4,
						icon: '../../static/icon/4.png'
					}
				],
				navs:[
				
					{
						title:'你有新的消息啦！'
					}
				]
			}
		},
		methods: {
			goList(value) {
				console.log('南京传媒学院-陈尔睿' + '&id=' + value.id)
			}
		},
		onPullDownRefresh() {
			setTimeout(()=>{
				uni.stopPullDownRefresh()
			},2000)//延迟刷新2秒
		}
	}
</script>

<style lang="scss">
.nav{
		display: flex;
		.na{
			width: 300rpx;
			height: 300rpx;
		}
		.nav_item{
			width: 75%;
			text-align: left;
			view{
				width: 200rpx;
				height: 100rpx;
				background:#FFFFFF;
				border-radius: 30rpx;
				margin: 5px;
				line-height: 220rpx;
				color:#333333;
			
				font-size: 40rpx;
				font-weight: bold;
			}
			text{
				line-height: 150rpx;
				color:#999999;
			}
			
		text{
				font-size: 30rpx;
			}
		}
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
		border-radius: 40upx;
		width: 120upx;
		height: 120upx;
	}
	
	.tag-text {
		font-size: 28upx;
		color: #FF80AB;
	}
	
</style>

