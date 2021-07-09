<template>
	<view class="content">
    <image class="logo" src="../../static/tabs/logo1.png"></image>
		<view class="input-group">
			<view class="input-row border">
				<text class="title">账号：</text>
				<m-input class="m-input" type="text" clearable focus v-model="account" placeholder="请输入账号"></m-input>
			</view>
			<view class="input-row">
				<text class="title">密码：</text>
				<m-input type="password" displayable v-model="password" placeholder="请输入密码"></m-input>
			</view>
		</view>
		<view class="btn-row">
			<button class="cu-btn bg-green block lg" @tap="bindLogin">登录</button>
		</view>
		<view class="action-row">
			<navigator url="../reg/reg">注册账号</navigator>
			<text>|</text>
			<navigator url="../pwd/pwd">忘记密码</navigator>
		</view>
	</view>
</template>

<script>
	import service from '../../service.js';
	import {
		mapState,
		mapMutations
	} from 'vuex'
	import mInput from '../../components/m-input.vue'

	export default {
		components: {
			mInput
		},
		data() {
			return {
				providerList: [],
				hasProvider: false,
				account: '',
				password: '',
				positionTop: 0,
				isDevtools: false,
			}
		},
		computed: mapState(['forcedLogin']),
		methods: {
			...mapMutations(['login']),
			
			initPosition() {
				
				this.positionTop = uni.getSystemInfoSync().windowHeight - 100;
			},
			bindLogin() {
				
				if (this.account.length < 5) {
					uni.showToast({
						icon: 'none',
						title: '账号最短为 5 个字符'
					});
					return;
				}
				if (this.password.length < 6) {
					uni.showToast({
						icon: 'none',
						title: '密码最短为 6 个字符'
					});
					return;
				}
				
				const data = {
					account: this.account,
					password: this.password
				};
				const validUser = service.getUsers().some(function(user) {
					return data.account === user.account && data.password === user.password;
				});
				if (validUser) {
          console.log(this.account)
					this.toMain(this.account);
				} else {
					uni.showToast({
						icon: 'none',
						title: '用户账号或密码不正确',
					});
				}
			},
			getUserInfo({
				detail
			}) {
				if (detail.userInfo) {
					this.toMain(detail.userInfo.nickName);
				} else {
					uni.showToast({
						icon: 'none',
						title: '登陆失败'
					});
				}
			},
			toMain(userName) {
				this.login(userName);
			
				if (this.forcedLogin) {
					uni.reLaunch({
						url:'../cc/1',
					});
				} else {
					uni.navigateBack();
				}

			}
		},
		onReady() {
			this.initPosition();
    },
	onPullDownRefresh() {
		setTimeout(()=>{
			uni.stopPullDownRefresh()
		},2000)//延迟刷新2秒
	}
	}
</script>

<style lang="scss">
	.action-row {
		display: flex;
		flex-direction: row;
		justify-content: center;
    color:$shop-color;
	}

	.action-row navigator {
    color:$shop-color;
		padding: 0 10px;
	}

  .logo {
    width: 250upx;
    height: 250upx;
    border-radius: 50%;
    margin: 50px auto 20px auto;
	
	
  }
  .content {
  	display: flex;
  	flex: 1;
  	flex-direction: column;
  	background-color: #FFFFFF;
  	padding: 10px;
  }
  .input-group {
  	background-color: #ffffff;
  	margin-top: 20px;
  	position: relative;
  }
  
  .input-group::before {
  	position: absolute;
  	right: 0;
  	top: 0;
  	left: 0;
  	height: 1px;
  	content: '';
  	-webkit-transform: scaleY(.5);
  	transform: scaleY(.5);
  	background-color: #c8c7cc;
  }
  
  .input-group::after {
  	position: absolute;
  	right: 0;
  	bottom: 0;
  	left: 0;
  	height: 1px;
  	content: '';
  	-webkit-transform: scaleY(.5);
  	transform: scaleY(.5);
  	background-color: #c8c7cc;
  }
  .input-row {
  		display: flex;
  		flex-direction: row;
  		position: relative;
  		font-size: 18px;
  		line-height: 40px;
  	}
  
  	.input-row .title {
  		width: 72px;
  		padding-left: 15px;
    color: $shop-color;
  	}
  
  	.input-row.border::after {
  		position: absolute;
  		right: 0;
  		bottom: 0;
  		left: 8px;
  		height: 1px;
  		content: '';
  		-webkit-transform: scaleY(.5);
  		transform: scaleY(.5);
  		background-color: #c8c7cc;
  	}
  
  .btn-row {
    padding:30px 0;
  }
  
</style>