<template>
	<view class="">
		<Tabs :tabs="tabs" bindtabsItemChange="handleTabsItemChange">
			<block v-if="tabs[0].isActive">
				<view class="first_tab">
					<navigator class="goods_item" v-for="(item, goods_id) in goodsList" :key="goods_id" :url="'/pages/shangjiaxiangqing/shangjiaxiangqing?goods_id=' + item.goods_id">
						<!-- 左侧 图片容器 -->
						<view class="goods_img_wrap">
							<image
								mode="widthFix"
								:src="item.goods_small_logo ? item.goods_small_logo : 'https://ww1.sinaimg.cn/large/007rAy9hgy1g24by9t530j30i20i2glm.jpg'"
							></image>
						</view>
						<!-- 右侧 商品容器 -->
						<view class="goods_info_wrap">
							<view>
								<view class="goods_name">{{ item.goods_name }}</view>
								<view class="goods_distance">{{ item.goods_distance }}</view>
							</view>
							<view class="qiye_zizhi">
								<image src="../../static/tubiao/资质证书.png" mode="widthFix" lazy-load></image>
								<view class="zizhi_mingcheng">{{ item.goods_zizhi }}</view>
							</view>

							<view class="yingye_shijian">
								<image src="../../static/tubiao/时钟.png" mode="widthFix" lazy-load></image>
								<view class="goods_time">{{ item.goods_time }}</view>
							</view>

							<view class="xiangxi_dizhi">
								<image src="../../static/tubiao/地图.png" mode="widthFix" lazy-load></image>
								<view class="goods_position">{{ item.goods_position }}</view>
							</view>
						</view>
					</navigator>
				</view>
			</block>
			<block v-else-if="tabs[1].isActive">1</block>
			<block v-else-if="tabs[2].isActive">2</block>
		</Tabs>
	</view>
</template>

<script>
export default {
	data() {
		return {
			tabs: [
				{
					id: 0,
					value: '综合',
					isActive: true
				},
				{
					id: 1,
					value: '附近',
					isActive: false
				},
				{
					id: 2,
					value: '新入',
					isActive: false
				}
			],
			goodsList: [
				{
					goods_id: 57445,
					cat_id: 9,
					goods_zizhi: '有害生物防治企业资质：国家一级',
					goods_name: '军友有害生物防治有限公司',
					goods_position: '深圳市龙华区福城街道桔塘社区桔坑路6号二单元320',
					goods_time: '8:00-2100',
					goods_distance: '80km',
					goods_number: 100,
					goods_weight: 100,
					goods_big_logo: '../../static/floor/军友200.jpg',
					goods_small_logo: '../../static/floor/军友200.jpg',
					add_time: 1516663280,
					upd_time: 1516663280,
					hot_mumber: 0,
					is_promote: false,
					cat_one_id: 1,
					cat_two_id: 3,
					cat_three_id: 9
				},
				{
					goods_id: 57445,
					cat_id: 9,
					goods_name: '军友有害生物防治有限公司',
					goods_zizhi: '有害生物防治：国家一级',
					goods_position: '深圳市龙华区福城街道桔塘社区桔坑路6号二单元320',
					goods_time: '8:00-2100',
					goods_distance: '80km',
					goods_number: 100,
					goods_weight: 100,
					goods_big_logo: '../../static/floor/军友200.jpg',
					goods_small_logo: '../../static/floor/军友200.jpg',
					add_time: 1516663280,
					upd_time: 1516663280,
					hot_mumber: 0,
					is_promote: false,
					cat_one_id: 1,
					cat_two_id: 3,
					cat_three_id: 9
				},
				{
					goods_id: 57445,
					cat_id: 9,
					goods_name: '军友有害生物防治有限公司',
					goods_zizhi: '有害生物防治：国家一级',
					goods_position: '深圳市龙华区福城街道桔塘社区桔坑路6号二单元320',
					goods_time: '8:00-2100',
					goods_distance: '80km',
					goods_number: 100,
					goods_weight: 100,
					goods_big_logo: '../../static/floor/军友200.jpg',
					goods_small_logo: '../../static/floor/军友200.jpg',
					add_time: 1516663280,
					upd_time: 1516663280,
					hot_mumber: 0,
					is_promote: false,
					cat_one_id: 1,
					cat_two_id: 3,
					cat_three_id: 9
				},
				{
					goods_id: 57445,
					cat_id: 9,
					goods_name: '军友有害生物防治有限公司',
					goods_zizhi: '有害生物防治：国家一级',
					goods_position: '深圳市龙华区福城街道桔塘社区桔坑路6号二单元320',
					goods_time: '8:00-2100',
					goods_distance: '80km',
					goods_number: 100,
					goods_weight: 100,
					goods_big_logo: '../../static/floor/军友200.jpg',
					goods_small_logo: '../../static/floor/军友200.jpg',
					add_time: 1516663280,
					upd_time: 1516663280,
					hot_mumber: 0,
					is_promote: false,
					cat_one_id: 1,
					cat_two_id: 3,
					cat_three_id: 9
				},
				{
					goods_id: 57445,
					cat_id: 9,
					goods_name: '军友有害生物防治有限公司',
					goods_zizhi: '有害生物防治：国家一级',
					goods_position: '深圳市龙华区福城街道桔塘社区桔坑路6号二单元320',
					goods_time: '8:00-2100',
					goods_distance: '80km',
					goods_number: 100,
					goods_weight: 100,
					goods_big_logo: '../../static/floor/军友200.jpg',
					goods_small_logo: '../../static/floor/军友200.jpg',
					add_time: 1516663280,
					upd_time: 1516663280,
					hot_mumber: 0,
					is_promote: false,
					cat_one_id: 1,
					cat_two_id: 3,
					cat_three_id: 9
				}
			],
			// 总页数
			totalPages: 1,
			QueryParams: {
				query: '',
				cid: '',
				pagenum: 1,
				pagesize: 10
			}
		};
	},
	onLoad: function(options) {
		this.QueryParams.cid = options.cid || '';
		this.QueryParams.query = options.query || '';
		// this.getGoodsList();
	},

	// 获取商品列表数据
	async getGoodsList() {
		const res = await request({ url: '/goods/search', data: this.QueryParams });
		// 获取 总条数
		const total = res.total;
		// 计算总页数
		this.totalPages = Math.ceil(total / this.QueryParams.pagesize);
		// console.log(this.totalPages);
		this.setData({
			// 拼接了数组
			goodsList: [...this.data.goodsList, ...res.goods]
		});

		// 关闭下拉刷新的窗口 如果没有调用下拉刷新的窗口 直接关闭也不会报错
		wx.stopPullDownRefresh();
	},

	// 标题点击事件 从子组件传递过来
	handleTabsItemChange(e) {
		// 1 获取被点击的标题索引
		const { index } = e.detail;
		// 2 修改源数组
		let { tabs } = this.data;
		tabs.forEach((v, i) => (i === index ? (v.isActive = true) : (v.isActive = false)));
		// 3 赋值到data中
		this.setData({
			tabs
		});
	},
	// 页面上滑 滚动条触底事件
	onReachBottom() {
		//  1 判断还有没有下一页数据
		if (this.QueryParams.pagenum >= this.totalPages) {
			// 没有下一页数据
			//  console.log('%c'+"没有下一页数据","color:red;font-size:100px;background-image:linear-gradient(to right,#0094ff,pink)");
			wx.showToast({ title: '没有下一页数据' });
		} else {
			// 还有下一页数据
			//  console.log('%c'+"有下一页数据","color:red;font-size:100px;background-image:linear-gradient(to right,#0094ff,pink)");
			this.QueryParams.pagenum++;
			this.getGoodsList();
		}
	},
	// 下拉刷新事件
	onPullDownRefresh() {
		// 1 重置数组
		this.setData({
			goodsList: []
		});
		// 2 重置页码
		this.QueryParams.pagenum = 1;
		// 3 发送请求
		this.getGoodsList();
	}
};
</script>

<style scoped>
/* pages/goods_list/index.wxss */
.first_tab .goods_item {
	display: flex;
	border-bottom: 1px solid #ccc;
}
.first_tab .goods_item .goods_img_wrap {
	flex: 2;
	display: flex;
	justify-content: center;
	align-items: center;
}
.first_tab .goods_item .goods_img_wrap image {
	width: 70%;
}
.first_tab .goods_item .goods_info_wrap {
	flex: 3;
	display: flex;
	flex-direction: column;
	justify-content: space-around;
}
.first_tab .goods_item .goods_info_wrap .goods_name {
	display: -webkit-box;
	overflow: hidden;
	width: 330upx;
	float: left;
	-webkit-box-orient: vertical;
	-webkit-line-clamp: 1;
	font-size: 26upx;
}
.first_tab .goods_item .goods_info_wrap .goods_time {
	color: var(--themeColor);
	font-size: 32rpx;
	margin-left: 50upx;
	font-size: 26upx;
	color: #F7F308;
}
.first_tab .goods_item .goods_info_wrap .goods_position {
	display: -webkit-box;
	overflow: hidden;
	-webkit-box-orient: vertical;
	-webkit-line-clamp: 1;
	margin-left: 50upx;
	font-size: 26upx;
	color: #C0C0C0;
}

.xiangxi_dizhi image,
.yingye_shijian image,
.qiye_zizhi image {
	float: left;
	width: 40upx;
}
.zizhi_mingcheng {
	display: -webkit-box;
	overflow: hidden;
	-webkit-box-orient: vertical;
	-webkit-line-clamp: 1;
	margin-left: 50upx;
	font-size: 26upx;
	color: #D81E06;
}
.goods_distance {
	font-size: 26upx;
	float: right;
	padding-right: 20upx;
	}
</style>
