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

<style>
	/* uni.css - 通用组件、模板样式库，可以当作一套ui库应用 */
	@import './common/uni.css';
	/*每个页面公共css */
	.icon{
    display: inline-block;
    background-repeat: no-repeat;
    background-position: center;
    background-size: 100% auto;
  }
  .icon.icon-star{
    background-image: url(./static/star.png);
    width: 32upx;
    height: 32upx;
  }
  .icon.icon-location{
    background-image: url(./static/location.png);
    width: 32upx;
    height: 32upx;
  }
  .icon.icon-djxx{
    background-image: url(./static/djxx.png);
    width: 40upx;
    height: 52upx;
  }
  .icon.icon-xxs{
    background-image: url(./static/xxs.png);
    width: 40upx;
    height: 52upx;
  }
  .icon.icon-home{
    background-image: url(./static/home.png);
    width: 80upx;
    height: 90upx;
  }
  .icon.icon-zzsh{
    background-image: url(./static/zzsh.png);
    width: 40upx;
    height: 52upx;
  }
  .icon.icon-wode{
    background-image: url(./static/wode.png);
    width: 40upx;
    height: 52upx;
  }
</style>
