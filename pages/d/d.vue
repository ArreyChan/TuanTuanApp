<template>
	<view>
		<view class="contact">
			<image class="img" src="../../static/picture/7.png"></image>
			<button type="primary" @click="redirectDetail()">客服直达</button>
			<button type="default" @click="redirectDetail()">厂家网址</button>
		</view>
		<view class="contact">
			<image class="img" src="../../static/picture/8.png"></image>
			<button type="primary" @click="redirectDetail()">客服直达</button>
			<button type="default" @click="redirectDetail()">厂家网址</button>
		</view>
		<view class="contact">
			<image class="img" src="../../static/picture/9.png"></image>
			<button type="primary" @click="redirectDetail()">客服直达</button>
			<button type="default" @click="redirectDetail()">厂家网址</button>
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
			redirectDetail(){
				uni.redirectTo({
					url:'http://www.cucn.edu.cn/'//只是跳转普通页面
				})
			}
		}
	}
</script>

<style lang="scss">
.contact{
	background: #FFFFFF;
	width: 750rpx;
	margin: 10rpx 0;
	padding:10rpx ;
	box-sizing: border-box;
	display: flex;
	flex-wrap: wrap;
	justify-content: space-between;
	.img{
		width: 750rpx;
		height:320rpx;
		display: block;
		margin: auto;
	}
}
</style>
