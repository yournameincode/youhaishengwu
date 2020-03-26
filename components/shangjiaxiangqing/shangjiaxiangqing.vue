<template>
	<view>
		<view class="detail_swiper">
			<swiper autoplay circular indicator-dots>
				<swiper-item v-for="(item, pics_id) in goodsObj.pics" :key="pics_id" bindtap="handlePrevewImage">
					<image mode="widthFix" :src="item.pics_mid"></image></swiper-item>
			</swiper>
		</view>
		<view class="goods_name_row">
			<view class="goods_name">{{ goodsObj.goods_name }}</view>
			<view class="goods_collect" bindtap="handleCollect">
				<text class="iconfont" :class="isCollect ? 'icon-shoucang1' : 'icon-shoucang'"></text>
				<view class="collect_text">收藏</view>
			</view>
		</view>
		<view class="goods_tel_row">
			<view class="goods_tel">商家电话：{{ goodsObj.goods_tel }}</view>
		</view>
		<view class="goods_position_row">
			<view class="goods_position">商家地址：{{ goodsObj.goods_position }}</view>
		</view>
		<view class="goods_info">
			<view class="goods_info_title">商家详情</view>
			<view class="goods_info_content">
				<!-- 富文本 -->
				<!-- {{goodsObj.goods_introduce}} -->
				<rich-text :nodes="goodsObj.goods_introduce"></rich-text>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			goodsObj: {
				goods_id: 8888, //通过点击商品列表的一个商品，伴随着点击事件传来goods_id，用于查询商家
				cat_id: 1085,
				goods_name: '军友有害生物防治有限公司',
				goods_position: '深圳市龙华区福城街道桔塘社区桔坑路6号二单元320',
				goods_time: '8:00-2100',
				goods_tel: '15070053433',
				goods_price: 500,
				goods_number: 100,
				goods_weight: 100,
				goods_introduce:
					'<div class="lazyimg"><p></p><p>经典武士大马士小直刀手工制作，外观设计独特，工艺精巧，，花纹独特高贵，优质钢材，硬度与韧性相结合，持久锋利，坚固耐用 ，是一款不可多得的典藏版世界名刀！ \n\n名 称：经典武士大马士革直刀\n全 长: 18.5cm\n刃 长: 9.8cm\n柄 长: 7cm\n硬 度: 59HRC\n刃 厚: 0.24cm\n重 量: 165克\n刃 材: 大马士革钢\n表 面: 大马士革钢特有的花纹原色\n柄材：黑檀木+铜头   配件：刀架</p><p><img picsize="32KB" data-src="//image.suning.cn/uimg/sop/phonecomm/714079715309577786595100_640x.jpg?from=mobile&amp;format=80q.webp" alt="" src="//image.suning.cn/uimg/sop/phonecomm/714079715309577786595100_640x.jpg?from=mobile&format=80q.webp" width="100%" height="auto"></p><p><img picsize="30KB" data-src="//image.suning.cn/uimg/sop/phonecomm/134618140543963944073230_640x.jpg?from=mobile&amp;format=80q.webp" alt="" src="//image.suning.cn/uimg/sop/phonecomm/134618140543963944073230_640x.jpg?from=mobile&format=80q.webp" width="100%" height="auto"></p><p><img picsize="21KB" data-src="//image.suning.cn/uimg/sop/phonecomm/921373401731958065405500_640x.jpg?from=mobile&amp;format=80q.webp" alt="" src="//image.suning.cn/uimg/sop/phonecomm/921373401731958065405500_640x.jpg?from=mobile&format=80q.webp" width="100%" height="auto"></p><p><img picsize="27KB" data-src="//image.suning.cn/uimg/sop/phonecomm/101008207715763285052196_640x.jpg?from=mobile&amp;format=80q.webp" alt="" src="//image.suning.cn/uimg/sop/phonecomm/101008207715763285052196_640x.jpg?from=mobile&format=80q.webp" width="100%" height="auto"></p><p><img picsize="24KB" data-src="//image.suning.cn/uimg/sop/phonecomm/688524703772205887427000_640x.jpg?from=mobile&amp;format=80q.webp" alt="" src="//image.suning.cn/uimg/sop/phonecomm/688524703772205887427000_640x.jpg?from=mobile&format=80q.webp" width="100%" height="auto"></p><p><img picsize="29KB" data-src="//image.suning.cn/uimg/sop/phonecomm/736763584325380865395400_640x.jpg?from=mobile&amp;format=80q.webp" alt="" src="//image.suning.cn/uimg/sop/phonecomm/736763584325380865395400_640x.jpg?from=mobile&format=80q.webp" width="100%" height="auto"></p><p><img picsize="20KB" data-src="//image.suning.cn/uimg/sop/phonecomm/163117364021093737985621_640x.jpg?from=mobile&amp;format=80q.webp" alt="" src="//image.suning.cn/uimg/sop/phonecomm/163117364021093737985621_640x.jpg?from=mobile&format=80q.webp" width="100%" height="auto"></p></div>',
				goods_big_logo: 'http://image1.suning.cn/uimg/b2c/newcatentries/0070134290-000000000149003877_1_800x800.jpg',
				goods_small_logo: 'http://image1.suning.cn/uimg/b2c/newcatentries/0070134290-000000000149003877_1_400x400.jpg',
				goods_state: 2,
				is_del: '0',
				add_time: 1516361489,
				upd_time: 1516361489,
				delete_time: null,
				hot_mumber: 0,
				is_promote: false,
				cat_one_id: 995,
				cat_two_id: 1075,
				cat_three_id: 1085,
				goods_cat: '995,1075,1085',
				pics: [
					{
						pics_id: 38711,
						goods_id: 8888,
						pics_big: '../../static/floor/军友200.jpg',
						pics_mid: '../../static/floor/军友200.jpg',
						pics_sma: '../../static/floor/军友200.jpg',
						pics_big_url: '../../static/floor/军友200.jpg',
						pics_mid_url: '../../static/floor/军友200.jpg',
						pics_sma_url: '../../static/floor/军友200.jpg'
					},
					{
						pics_id: 38712,
						goods_id: 8888,
						pics_big: '../../static/floor/广东.jpg',
						pics_mid: '../../static/floor/军友200.jpg',
						pics_sma: '../../static/floor/明洁.jpg',
						pics_big_url: '../../static/floor/金诺.jpg',
						pics_mid_url: '../../static/floor/成都市.jpg',
						pics_sma_url: '../../static/floor/军友200.jpg'
					},
					{
						pics_id: 38713,
						goods_id: 8888,
						pics_big: '../../static/floor/广东.jpg',
						pics_mid: '../../static/floor/广东.jpg',
						pics_sma: '../../static/floor/广东.jpg',
						pics_big_url: '../../static/floor/军友200.jpg',
						pics_mid_url: '../../static/floor/军友200.jpg',
						pics_sma_url: '../../static/floor/军友200.jpg'
					},
					{
						pics_id: 38714,
						goods_id: 8888,
						pics_big: '../../static/floor/军友200.jpg',
						pics_mid: '../../static/floor/明洁.jpg',
						pics_sma: '../../static/floor/军友200.jpg',
						pics_big_url: '../../static/floor/军友200.jpg',
						pics_mid_url: '../../static/floor/军友200.jpg',
						pics_sma_url: '../../static/floor/军友200.jpg'
					},
					{
						pics_id: 38715,
						goods_id: 8888,
						pics_big: '../../static/floor/军友200.jpg',
						pics_mid: '../../static/floor/金诺.jpg',
						pics_sma: '../../static/floor/军友200.jpg',
						pics_big_url: '../../static/floor/军友200.jpg',
						pics_mid_url: '../../static/floor/军友200.jpg',
						pics_sma_url: '../../static/floor/军友200.jpg'
					}
				],
				attrs: [
					{
						goods_id: 8888,
						attr_id: 9210,
						attr_value: '户外直刀',
						add_price: 0,
						attr_name: '主体参数-类别',
						attr_sel: 'only',
						attr_write: 'manual',
						attr_vals: '放大镜'
					},
					{
						goods_id: 8888,
						attr_id: 9209,
						attr_value: '攀岩,探洞 ,救援,工程保护 ,高空作业,露营',
						add_price: 0,
						attr_name: '功能参数-适用范围',
						attr_sel: 'only',
						attr_write: 'manual',
						attr_vals: '攀岩,探洞 ,垂降,救援,工程保护 ,高空作业,露营,旅游'
					}
				]
			},
			// 商品是否被收藏
			isCollect: false,

			// 商品对象
			GoodsInfo: {}
			/**
			 * 生命周期函数--监听页面加载
			 */
		};
	},
	onShow: function() {
		let pages = getCurrentPages();
		let currentPage = pages[pages.length - 1];
		let options = currentPage.options;
		const { goods_id } = options;
		// this.getGoodsDetail(goods_id);
	},
	methods: {
		async getGoodsDetail(goods_id) {
			const goodsObj = await request({ url: '/goods/detail', data: { goods_id } });
			this.GoodsInfo = goodsObj;
			// 1 获取缓存中的商品收藏的数组
			let collect = wx.getStorageSync('collect') || [];
			// 2 判断当前商品是否被收藏
			let isCollect = collect.some(v => v.goods_id === this.GoodsInfo.goods_id);
			this.setData({
				goodsObj: {
					goods_name: goodsObj.goods_name,
					goods_price: goodsObj.goods_price,
					// iphone部分手机 不识别 webp图片格式
					// 最好找到后台 让他进行修改
					// 临时自己改 确保后台存在 1.webp => 1.jpg
					goods_introduce: goodsObj.goods_introduce.replace(/\.webp/g, '.jpg'),
					pics: goodsObj.pics
				},
				isCollect
			});
		},
		// 点击轮播图 放大预览
		handlePrevewImage(e) {
			// 1 先构造要预览的图片数组
			const urls = this.GoodsInfo.pics.map(v => v.pics_mid);
			// 2 接收传递过来的图片url
			const current = e.currentTarget.dataset.url;
			wx.previewImage({
				current,
				urls
			});
		},
		// 点击 加入购物车
		handleCartAdd() {
			// 1 获取缓存中的购物车 数组
			let cart = wx.getStorageSync('cart') || [];
			// 2 判断 商品对象是否存在于购物车数组中
			let index = cart.findIndex(v => v.goods_id === this.GoodsInfo.goods_id);
			if (index === -1) {
				//3  不存在 第一次添加
				this.GoodsInfo.num = 1;
				this.GoodsInfo.checked = true;
				cart.push(this.GoodsInfo);
			} else {
				// 4 已经存在购物车数据 执行 num++
				cart[index].num++;
			}
			// 5 把购物车重新添加回缓存中
			wx.setStorageSync('cart', cart);
			// 6 弹窗提示
			wx.showToast({
				title: '加入成功',
				icon: 'success',
				// true 防止用户 手抖 疯狂点击按钮
				mask: true
			});
		},
		// 点击 商品收藏图标
		handleCollect() {
			let isCollect = false;
			// 1 获取缓存中的商品收藏数组
			let collect = wx.getStorageSync('collect') || [];
			// 2 判断该商品是否被收藏过
			let index = collect.findIndex(v => v.goods_id === this.GoodsInfo.goods_id);
			// 3 当index！=-1表示 已经收藏过
			if (index !== -1) {
				// 能找到 已经收藏过了  在数组中删除该商品
				collect.splice(index, 1);
				isCollect = false;
				wx.showToast({
					title: '取消成功',
					icon: 'success',
					mask: true
				});
			} else {
				// 没有收藏过
				collect.push(this.GoodsInfo);
				isCollect = true;
				wx.showToast({
					title: '收藏成功',
					icon: 'success',
					mask: true
				});
			}
			// 4 把数组存入到缓存中
			wx.setStorageSync('collect', collect);
			// 5 修改data中的属性  isCollect
			this.setData({
				isCollect
			});
		}
	}
	// 获取商品详情数据
};
</script>

<style scoped>
page {
	padding-bottom: 0rpx;
}
.detail_swiper swiper {
	height: 100vw;
	text-align: center;
}
.detail_swiper swiper-item{
}
	
.detail_swiper swiper image {
	width: 100%;
}
.goods_price {
	padding: 15rpx;
	font-size: 32rpx;
	font-weight: 600;
	color: var(--themeColor);
}
.goods_name_row {
	border-top: 5rpx solid #dedede;
	border-bottom: 5rpx solid #dedede;
	padding: 10rpx 0;
	display: flex;
}
.goods_name_row .goods_name {
	flex: 5;
	color: #000;
	font-size: 40rpx;
	padding: 15rpx 15rpx;
	display: -webkit-box;
	overflow: hidden;
	-webkit-box-orient: vertical;
	-webkit-line-clamp: 2;
}
.goods_name_row .goods_collect {
	flex: 1;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	border-left: 1rpx solid #000;
}
.goods_name_row .goods_collect .icon-shoucang1 {
	color: orangered;
}
.goods_tel_row,
.goods_position_row {
	border-top: 5rpx solid #dedede;
	border-bottom: 5rpx solid #dedede;
	padding: 10rpx 0;
	display: flex;
}
.goods_tel_row .goods_tel,
.goods_position_row .goods_tel {
	flex: 5;
	color: #000;
	font-size: 40rpx;
	padding: 15rpx 15rpx;
}
.goods_tel_row .goods_position,
.goods_position_row .goods_position {
	flex: 5;
	color: #000;
	font-size: 40rpx;
	padding: 15rpx 15rpx;
}
.goods_info .goods_info_title {
	font-size: 32rpx;
	color: var(--themeColor);
	font-weight: 600;
	padding: 20rpx;
}
.btm_tool {
	border-top: 1rpx solid #ccc;
	position: fixed;
	left: 0;
	bottom: 0;
	width: 100%;
	height: 90rpx;
	background-color: #fff;
	display: flex;
}
.btm_tool .tool_item {
	flex: 1;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	font-size: 24rpx;
	position: relative;
}
.btm_tool .tool_item button {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	opacity: 0;
}
.btm_tool .btn_cart {
	flex: 2;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	background-color: #ffa500;
	color: #fff;
	font-size: 30rpx;
	font-weight: 600;
}
.btm_tool .btn_buy {
	flex: 2;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	background-color: #eb4450;
	color: #fff;
	font-size: 30rpx;
	font-weight: 600;
}
</style>
