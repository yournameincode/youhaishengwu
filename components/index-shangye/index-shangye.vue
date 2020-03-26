<template>
	<view>
		<!-- 标题 -->
		<view class="floor_title"><image mode="widthFix" :src="titleImageSrc"></image></view>
		<!-- 内容 -->
		<view class="floor_list">
			<navigator v-for="(item2, index2) in productList" :key="index2"  :url="item2.navigatorUrl">
				<image :mode="index2===0?'widthFix':'scaleToFill'" :src="item2.imageSrc"></image>
			</navigator>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			titleImageSrc: '../../static/headNews/商圈头条1.jpg',
			productList: [
				{ imageSrc: '../../static/headNews/说虫.jpg',navigatorUrl:'' },
				{ imageSrc: '../../static/headNews/VR.jpg',navigatorUrl:'' },
				{ imageSrc: '../../static/headNews/交流.jpg',navigatorUrl:'' },
				{ imageSrc: '../../static/headNews/招聘.jpg' ,navigatorUrl:''},
				{ imageSrc: '../../static/headNews/招投标.jpg',navigatorUrl:'' }
			],
			
			// floorList:[{title_image_src:"../../static/headNews/商圈头条1.jpg",
			// 			product_list:[{image_src:"../../static/headNews/说虫.jpg"},
			// 			{image_src:"../../static/headNews/VR.jpg"},
			// 			{image_src:"../../static/headNews/交流.jpg"},
			// 			{image_src:"../../static/headNews/招聘.jpg"},
			// 			{image_src:"../../static/headNews/招投标.jpg"}
			// 			]
			// }]
		};
	}
};
</script>

<style scoped>
.floor_title {
	padding-top: 10rpx;
}

.floor_list {
	overflow: hidden;
}
.floor_list navigator {
	float: left;
	width: 33.3%;
	/* 后四个超链接 */
	/* 2 3 两个超链接 */
}
.floor_list navigator:nth-last-child(-n + 4) {
	/* 原图的宽高 232 *386 */
	height: 27.72711207vw;
}
.floor_list navigator:nth-child(2),
.floor_list navigator:nth-child(3) {

}
.floor_list navigator image {
	width: 100%;
	height: 100%;
}
</style>
