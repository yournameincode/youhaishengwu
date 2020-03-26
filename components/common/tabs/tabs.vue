<template>
	<view class="content">
		<ms-tabs :list="type2" v-model="active2" itemColor="#03A9F4" lineColor="#03A9F4" :lineAnimated="false"></ms-tabs>
	</view>
</template>

<script>
import msTabs from '@/components/common/ms-tabs/ms-tabs.vue';
export default {
	components: {
		msTabs
	},
	data() {
		return {
			type2: [
				{
					title: '综合'
				},
				{
					title: '附件'
				},
				{
					title: '新入'
				}
			],

			active2: 0
		};
	},
	watch: {
		active() {
			console.log(this.active); // 0
		}
	},
	// onShow() {},
	// methods: {
	// 	setTabsValue() {
	// 		this.type5 = this.type2;
	// 		this.active5 = 4;
	// 	}
	// }
};
</script>

<style lang="scss">
.content {
	background: #fff;
	margin-bottom: 20rpx;
	.title {
		margin-left: 20rpx;
		padding: 20rpx 0;
		color: #818586;
		border-bottom: 1px solid #f6f6f6;
	}
}
</style>
