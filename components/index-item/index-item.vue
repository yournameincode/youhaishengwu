<template>
	<view class="cate-section">
		<view class="cate-item"><image src="../../static/cates/index-cate5.jpg"></image>
		<text>产品发布</text>
		</view>
		<view class="cate-item"><image src="../../static/cates/index-cate6.jpg"></image>
		<text>跳蚤市场</text>
		</view>
		<view class="cate-item"><image src="../../static/cates/index-cate7.jpg"></image>
		<text>求职招聘</text>
		</view>
		<view class="cate-item"><image src="../../static/cates/index-cate8.jpg"></image>
		<text>行业招标</text>
		</view>
	</view>
</template>

<script>
</script>

<style scoped>
	.cate-section {
		display: flex;
		justify-content: space-around;
		align-items: center;
		flex-wrap:wrap;
		padding: 30upx 22upx; 
		background: #fff;
}
		.cate-item{
			display: flex;
			flex-direction: column;
			align-items: center;
			font-size: $font-sm;
			color: $font-color-dark;
		}
		/* 原图标颜色太深,不想改图了,所以加了透明度 */
		image {
			width: 88upx;
			height: 88upx;
			margin-bottom: 14upx;
			border-radius: 50%;
			opacity: .7;
			box-shadow: 4upx 4upx 20upx rgba(250, 67, 106, 0.3);
		}
	
</style>
