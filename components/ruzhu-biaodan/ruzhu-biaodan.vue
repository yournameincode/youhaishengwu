<template>
	<view>
		<form>
			<view class="cu-form-group">
				<view class="title">商家名称</view>
				<input placeholder="请输入商家名称" name="input"></input>
			</view>
			<view class="cu-form-group">
				<view class="title">详细地址</view>
				<input placeholder="请输入详细地址" name="input"></input>
				<text class='cuIcon-locationfill text-orange'></text>
			</view>
			<view class="cu-form-group">
				<view class="title">手机号码</view>
				<input placeholder="输入框带标签" name="input"></input>
				<view class="cu-capsule radius">
					<view class='cu-tag bg-blue '>
						+86
					</view>
					<view class="cu-tag line-blue">
						中国大陆
					</view>
				</view>
			</view>
		<view class="cu-form-group">
			<view class="title">营业时间</view>
			<input placeholder="9:00-21:00" name="input"></input>
		</view>
			<view class="cu-form-group margin-top">
				<textarea maxlength="-1" :disabled="modalName!=null" @input="textareaAInput" placeholder="请输入商家介绍"></textarea>
			</view>
			<view class="cu-bar bg-white margin-top">
				<view class="action">
					商家门面
				</view>
				<view class="action">
					{{imgList.length}}/9
				</view>
			</view>
			<view class="cu-form-group">
				<view class="grid col-4 grid-square flex-sub">
					<view class="bg-img" v-for="(item,index) in imgList" :key="index" @tap="ViewImage" :data-url="imgList[index]">
					 <image :src="imgList[index]" mode="aspectFill"></image>
						<view class="cu-tag bg-red" @tap.stop="DelImg" :data-index="index">
							<text class='cuIcon-close'></text>
						</view>
					</view>
					<view class="solids" @tap="ChooseImage" v-if="imgList.length<9">
						<text class='cuIcon-cameraadd'></text>
					</view>
				</view>
			</view>
			<view class="uni-padding-wrap uni-common-mt">
				 <button type="primary">确定发布</button>
			</view>
		</form>
		
	</view>
	
</template>

<script>
	export default {
		data() {
			return {
				index: -1,			
				time: '9:00-21:00',
				date: '2018-12-25',
				imgList: [],
				modalName: null,
				textareaAValue: '',
						
			};
		},
		methods: {
			
			TimeChange(e) {
				this.time = e.detail.value
			},

			ChooseImage() {
				uni.chooseImage({
					count: 9, //默认9
					sizeType: ['original', 'compressed'], //可以指定是原图还是压缩图，默认二者都有
					sourceType: ['album'], //从相册选择
					success: (res) => {
						if (this.imgList.length != 0) {
							this.imgList = this.imgList.concat(res.tempFilePaths)
						} else {
							this.imgList = res.tempFilePaths
						}
					}
				});
			},
			ViewImage(e) {
				uni.previewImage({
					urls: this.imgList,
					current: e.currentTarget.dataset.url
				});
			},
			DelImg(e) {
				uni.showModal({
					title: '召唤师',
					content: '确定要删除这段回忆吗？',
					cancelText: '再看看',
					confirmText: '再见',
					success: res => {
						if (res.confirm) {
							this.imgList.splice(e.currentTarget.dataset.index, 1)
						}
					}
				})
			},
			textareaAInput(e) {
				this.textareaAValue = e.detail.value
			},
		}
	}
</script>

<style scoped>
	.cu-form-group .title {
		min-width: calc(4em + 15px);
	}
	.uni-common-mt{
		margin-left: 22rpx;
	}
</style>
