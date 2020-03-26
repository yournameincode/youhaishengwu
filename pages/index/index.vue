<template>
	<view>
		<!-- 搜索框 -->
		<view class="example-body"><uni-search-bar radius="100" placeholder="产品信息发布、找商家、找工作、产品采购、考证" @confirm="search" /></view>
		<!-- 轮播图 -->
		<view><bw-swiper :swiperList="swiperList" style="width:100%"></bw-swiper></view>
		<!-- 选项 -->
		<view><indexItem></indexItem></view>
		<!-- 热门商家 -->
		<view><screenTextScroll></screenTextScroll></view>
		<!-- 商业头条 -->
		<!-- 楼层 开始 -->
		<view><index-shangye></index-shangye></view>
		
	</view>
</template>

<script>
import uniSearchBar from '../../components/uni-search-bar/uni-search-bar.vue';
import bwSwiper from '../../components/bw-swiper/bw-swiper.vue';
import indexItem from '../../components/index-item/index-item.vue';
import screenTextScroll from '../../components/screenTextScroll/screenTextScroll.vue';
import indexShangye from '../../components/index-shangye/index-shangye.vue';


export default {
	components: {
		uniSearchBar,
		bwSwiper,
		indexItem,
		indexShangye,
		screenTextScroll
	},
	data() {
		return {
			searchVal: '',
			swiperList: [{ img: '../../static/index-swapers/4.jpg' }, { img: '../../static/index-swapers/1.jpg' }, { img: '../../static/index-swapers/2.jpg' }]
		};
	},
	methods: {
		search(res) {
			uni.showToast({
				title: '搜索：' + res.value,
				icon: 'none'
			});
		},
		input(res) {
			this.searchVal = res.value;
		},
		cancel(res) {
			uni.showToast({
				title: '点击取消，输入值为：' + res.value,
				icon: 'none'
			});
		}
	},
	onBackPress() {
		// #ifdef APP-PLUS
		plus.key.hideSoftKeybord();
		// #endif
	}
};
</script>

<style>
/* #ifndef APP-NVUE */
page {
	display: flex;
	flex-direction: column;
	box-sizing: border-box;
	background-color: white;
	min-height: 100%;
	height: auto;
}

view {
	font-size: 14px;
	line-height: inherit;
}

.example-body {
	flex-direction: row;
	flex-wrap: wrap;
	justify-content: center;
	padding: 0;
	font-size: 14px;
	background-color: #ffffff;
}
</style>
