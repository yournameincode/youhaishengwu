<template>
	<view class="seckill-section m-t">
		<view class="s-header">
			<image class="s-img" src="/static/floor/热门商家1.jpg" mode="widthFix"></image>
			<text class="s-text">更多 ></text>
		</view>
		<vue-seamless-scroll :data="goodsList" :class-option="optionLeft" class="seamless-warp2">
			<ul class="item">
				<li v-for="(item, index) in goodsList" :key="index">
					<view class="floor-item" @click="navToDetailPage(item)">
						<image :src="item.image" mode="aspectFill"></image>
						<text class="title clamp">{{ item.title }}</text>
					</view>
				</li>
			</ul>
		</vue-seamless-scroll>
	</view>
</template>

<script>
	export default {
	data() {
		return {
			goodsList: [
				{ image: '../../static/floor/成都市.jpg', title: '成都市成都市' },
				{ image: '../../static/floor/广东.jpg', title: '广东广东' },
				{ image: '../../static/floor/金诺.jpg', title: '金诺金诺' },
				{ image: '../../static/floor/广东.jpg', title: '广东广东' },
				{ image: '../../static/floor/广东.jpg', title: '广东广东' },
				{ image: '../../static/floor/广东.jpg', title: '广东广东' },
				{ image: '../../static/floor/军友.jpg', title: '军友军友' },
				{ image: '../../static/floor/明洁.jpg', title: '明洁明洁' }
			]
		};
	},
	computed: {
		optionLeft() {
			return {
				direction: 2,
				limitMoveNum: 2
			};
		}
	},
	methods: {
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

<style lang="scss" scoped>
.seamless-warp2 {
	overflow: hidden;
	height: 25px;
	width: 380px;
	ul.item {
		width: 580px;
		li {
			float: left;
			margin-right: 10px;
		}
	}
}

.seckill-section {
	padding: 4upx 10upx 24upx;
	background: #fff;
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
.s-text {
	flex: 2;
	margin-left: 200upx;
}
.m-t {
	margin-top: 10upx;
}
// .tip {
// 	font-size: $font-base;
// 	color: $font-color-light;
// 	margin: 0 20upx 0 40upx;
// }
// .timer {
// 	display: inline-block;
// 	width: 40upx;
// 	height: 36upx;
// 	text-align: center;
// 	line-height: 36upx;
// 	margin-right: 14upx;
// 	font-size: $font-sm + 2upx;
// 	color: #fff;
// 	border-radius: 2px;
// 	background: rgba(0, 0, 0, 0.8);
// }
// .icon-you {
// 	font-size: $font-lg;
// 	color: $font-color-light;
// 	flex: 1;
// 	text-align: right;
// }

// .floor-list {
// 	white-space: nowrap;
// }
// .scoll-wrapper {
// 	display: flex;
// 	align-items: flex-start;
// }
.floor-item {
	width: 150upx;
	margin-right: 20upx;
	font-size:  28upx;
	color: "white";
	line-height: 1.8;
}
.floor-list image {
	width: 120upx;
	height: 120upx;
	border-radius: 6upx;
}
.floor-list text {
	overflow: hidden;
	text-overflow: ellipsis;
	white-space: nowrap;
	display: block;
}
</style>