<template>
    <view>
            <uni-segmented-control :current="current" :values="items" @clickItem="onClickItem" style-type="button" active-color="#ff758c"></uni-segmented-control>
            <view class="content">
                <view v-show="current === 0">
                   <view>配饰（多选）</view>
                           <ld-select :multiple="true" :list="options"
                           list-key="label" value-key="value"
                           placeholder="请选择"
                           clearable
                           v-model="value2"
                           @change="selectChange2"></ld-select>
					<button type='default' @click="chooseImg">上传印花图稿</button>	
					<view>选择布料材质及颜色</view>
					        <ld-select :multiple="true" :list="options"
					        list-key="label" value-key="value"
					        cancelText="取消"
					        confirmText="选定"
					        placeholder="请选择"
					        selectColor="#ecf8ff"
					        selectBgColor="#ff758c"
					        bgColor="#ecf8ff"
					        clearable
					        v-model="value4"
					        @change="selectChange4"></ld-select>
					<button type="default" class="bb">创作完成</button>
                </view>
				
				
                <view v-show="current === 1">
                   <button type='default' @click="chooseImg">上传崽崽图稿</button>
                   <text class='aa' >请先选择“上传图片”，点击"开始生成"进入小程序，来试试我们的3D虚拟技术吧</text>
				   <button type="default" class="bb">开始生成</button>
				   <button type='primary' @click="goDetail">联系娃厂</button>
                </view>
              
            </view>
        </view>
</template>
<script>
import uniSegmentedControl from "@/components/uni-segmented-control/uni-segmented-control.vue"
import ldSelect from '@/components/ld-select/ld-select.vue'
export default {
    components: {
		uniSegmentedControl,
		ldSelect
	}, 
    data() {
        return {
            items: ['形制','崽'],
            current: 0,
			options: [
				{
			    value: '选项1',
			    label: '帽子'
			    }, 
				{
				value: '选项2',
			    label: '鞋子'
			     }, {
			      value: '选项3',
			      label: '领结'
			     },
				 {
					 value:'选项4',
					 label:'腰带'
					 },
					 {
					  value:'选项4',
					 label:'cucn',
					 }
				 ],
				  value2: [],
				  value4: []
        }
    },
    methods: {
        onClickItem(e) {
            if (this.current !== e.currentIndex) {
                this.current = e.currentIndex;
            }
        },
		chooseImg(){
			uni.chooseImage({
				count:4,
				success: res=>{
					this.imgArr=res.tempFilePaths//上传图片方法
				}
			})
		},
		goDetail(){
			uni.navigateTo({
				url:"../d/d"
			})
		},
		selectChange2(val){
		                this.value2 = val
		            }
    }
}
</script>

<style lang="scss">
	.aa{
			height: 20px;
			line-height:50px;
			color: $shop-color;
			text-align: center;
			background: #FFFFFF;
			font-size: 30rpx;
			
		}
	.bb{
		color: #FF80AB;
	}
	 .main{
	        font-size: 32rpx;
	        padding: 20rpx;
	    }
</style>
<!-- <template>
	<view>
		<button type='default' @click="chooseImg">上传印花图稿</button>
		<text class='aa' >请先选择“上传图片”，点击上传的图片，来试试我们的3D虚拟技术吧</text>
		<image v-for="item in imgArr" v-bind:src="item" @click="previewImg" v-bind:key="item" class='dd'></image>
		<uni-grid :column="3" :show-border="true"  :square="true">
		    <uni-grid-item>
		        <text class="text">形制</text>
		    </uni-grid-item>
		    <uni-grid-item>
		        <text class="text">衣服</text>
		    </uni-grid-item>
		    <uni-grid-item>
		        <text class="text">布料</text>
		    </uni-grid-item>
		    <uni-grid-item>
		        <text class="text">颜色</text>
		    </uni-grid-item>
		    <uni-grid-item>
		        <text class="text">配饰</text>
		    </uni-grid-item>
		    <uni-grid-item>
		        <text class="text">其他</text>
		    </uni-grid-item>
		</uni-grid>
		<button type="default">开始创建</button>
		<button type='primary' @click="goDetail">联系娃厂</button>
	</view>
</template>

<script>
	import uniGrid from "@/components/uni-grid/uni-grid.vue"
	import uniGridItem from "@/components/uni-grid-item/uni-grid-item.vue"
	export default{
		data(){
			return{
				imgArr:[]
			}
		},
		methods:{
			chooseImg(){
				uni.chooseImage({
					count:4,
					success: res=>{
						this.imgArr=res.tempFilePaths//上传图片方法
					}
				})
			},
			goDetail(){
				uni.navigateTo({
					url:"../d/d"
				})
			}
		},
		onPullDownRefresh() {
			setTimeout(()=>{
				uni.stopPullDownRefresh()
			},2000)//延迟刷新2秒
		},
		previewImg(current){
			console.log(current)
			uni.previewImage({
				current,
				urls:this.imgArr,
				loop:true,
				indicator:'number'
			})
		},
		components: {uniGrid,uniGridItem}
		
	}
		
	
</script>

<style lang="scss">
	
.text{
	text-align: center;
	color: $shop-color;
	padding-top: 100rpx;
}
.dd{
		background: #FFFFFF;
		width: 750rpx;
		height: 750rpx;
		margin: 10rpx 0;
		padding:10rpx ;
		box-sizing: border-box;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
	}
.aa{
		height: 80px;
		line-height:80px;
		color: $shop-color;
		text-align: center;
		background: #FFFFFF;
		font-size: 25rpx;
		
	}
</style>
 -->