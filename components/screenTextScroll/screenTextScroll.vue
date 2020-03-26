<!-- 
展示屏幕文字滚动效果
 
使用方法：

 -->
<!-- 
展示屏幕文字滚动效果

usage:
 list:数组数据
 @getCurrentIndex  获取当前swiper的下标
 <textscroll :list="list" @getCurrentIndex="getIndex"/>

 -->

<template>
	<view class="seckill-section m-t">
		<view class="s-header">
			<image class="s-img" src="/static/floor/热门商家1.jpg" mode="widthFix"></image>
			<text class="s-text">更多 ></text>
		</view>

	<view class="floor-list">
		<swiper @change="slideChange" indicator-dots="false" autoplay="true" :interval="interval" circular="true"
		 display-multiple-items="2" :duration="duration">
			<swiper-item class="scoll-wrapper">
				<view class="scoll-wrapper">
					<view v-for="(item, index) in goodsList" :key="index" class="floor-item" @click="navToDetailPage(item)">
						<image :src="item.image" mode="aspectFill"></image>
						<text class="title clamp">{{ item.title }}</text>
					</view>
				</view>
			</swiper-item>
			<swiper-item class="scoll-wrapper">
				<view class="scoll-wrapper">
					<view v-for="(item, index) in goodsList1" :key="index" class="floor-item" @click="navToDetailPage(item)">
						<image :src="item.image" mode="aspectFill"></image>
						<text class="title clamp">{{ item.title }}</text>
					</view>
				</view>
			</swiper-item>
			<swiper-item class="scoll-wrapper">
				<view class="scoll-wrapper">
					<view v-for="(item, index) in goodsList2" :key="index" class="floor-item" @click="navToDetailPage(item)">
						<image :src="item.image" mode="aspectFill"></image>
						<text class="title clamp">{{ item.title }}</text>
					</view>
				</view>
			</swiper-item>
		</swiper>
	</view>
	</view>
	<!-- 
	 <scroll-view class="floor-list" scroll-x>

	 	</scroll-view>
	 
	 
	 -->
</template>



<script>
	export default {
		// props: {
		// 	//显示数据
		// 	list: {
		// 		type: Array,
		// 		defual:function(){
		// 			return [];
		// 		}
		// 	},
		// },
		data() {
			return {
				interval:3000,
				duration:12000,
				goodsList: [
					{ image: '../../static/floor/成都市.jpg', title: '成都市成都市' },
					{ image: '../../static/floor/成都市.jpg', title: '成都市成都市' },
					{ image: '../../static/floor/成都市.jpg', title: '成都市成都市' },

				],
				goodsList1: [
					
					{ image: '../../static/floor/广东.jpg', title: '广东广东' },
					{ image: '../../static/floor/广东.jpg', title: '广东广东' },
						{ image: '../../static/floor/广东.jpg', title: '广东广东' },

				],
				goodsList2: [
				
					{ image: '../../static/floor/明洁.jpg', title: '明洁明洁' },
					{ image: '../../static/floor/明洁.jpg', title: '明洁明洁' },
					{ image: '../../static/floor/明洁.jpg', title: '明洁明洁' },
				],
			};
		},
		methods:{
			slideChange(e){
				this.$emit('getCurrentIndex',e.detail.current); 
				
			},
			navToDetailPage(item) {
				//测试数据没有写id，用title代替
				let id = item.title;
				uni.navigateTo({
					url: `/pages/product/product?id=${id}`
				});
			}
		}

	};
</script>

<style scoped>
	.seckill-section {
		padding: 4upx 10upx 24upx;
		background: #fff;
		width: 100%;
	}
	.s-header {
		display: flex;
		align-items: center;
		height: 120upx;
		line-height: 1;
	}
	.s-img {
		height: 30upx;
		flex: 5;
	}
	.s-text{
		flex: 2;
		margin-left: 200upx;
	}
	.m-t {
		margin-top: 10upx;
	}
	.tip {
		font-size: $font-base;
		color: $font-color-light;
		margin: 0 20upx 0 40upx;
	}
	.timer {
		display: inline-block;
		width: 40upx;
		height: 36upx;
		text-align: center;
		line-height: 36upx;
		margin-right: 14upx;
		font-size: $font-sm + 2upx;
		color: #fff;
		border-radius: 2px;
		background: rgba(0, 0, 0, 0.8);
	}
	.icon-you {
		font-size: $font-lg;
		color: $font-color-light;
		flex: 1;
		text-align: right;
	}
	
	.floor-list {
		white-space: nowrap;
		height: 180upx;
		overflow: hidden;
	}
	.scoll-wrapper {
		display: flex;
		align-items: flex-start;
	}
	.floor-item {
		width: 104upx;
		margin-right: 20upx;
		font-size: 24upx;
		color: $font-color-dark;
		line-height: 1.8;
	}
	.floor-list image {
		width: 120upx;
		height: 120upx;
		border-radius: 6upx;
	}
	.floor-list text{
		overflow: hidden;
		white-space: nowrap;
		display: block;
	
	}
</style>
