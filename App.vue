<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
			const domModule = weex.requireModule('dom')
			domModule.addRule('fontFace', {
				'fontFamily': "iconfont",
				'src': "url('http://at.alicdn.com/t/c/font_3668475_c96lm4pzfnp.ttf?t=1663925251973')"
			});
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	@import url('/common/common.css');
	@import url('/common/free.css');
	/* #ifdef APP-PLUS-NVUE */
	@import url("/common/icon.css");
	/* #endif */
</style>
