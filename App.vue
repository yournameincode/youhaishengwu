<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	/*每个页面公共css */
	@import './common/uni.css';
	@import './common/icon.css';
	@import './common/common.css';
	/* 引入动画库 */
	@import './common/animate.css';
	@import "./common/colorui/main.css";
	@import "./common/colorui/icon.css";
	@import "/static/iconfont/font.scss";
	
</style>
