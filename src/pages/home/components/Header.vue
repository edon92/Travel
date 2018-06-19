<template>
	<div class="header">
		<div class="header-left">
			<span class="iconfont icon-back">&#xe624;</span>
		</div>
		<div class="header-input" placeholder="请输入">
		<span class="iconfont icon-input">&#xe632;</span>
		输入城市/景点/游玩主题
		</div>
			<router-link to="/city">
				<div class="header-right">
						{{this.city}}
						<span class="iconfont icon-arrow">&#xe64a;</span>
				</div>
			</router-link>
	</div>
</template>
<script type="text/javascript">
export default {
  name: 'HomeHeader',
  props: {
  	city: String
  }
}
</script>
<style type='text/stylus' lang='stylus' scoped>
	@import '~styles/varible.styl'
	.header
		display: flex
		line-height $headerHeight
		height: $headerHeight
		background: $bgcolor
		color: #fff
	.header-left
		width: .64rem	
		float: left
		text-align:center
		.icon-back
			height:	.86rem
			font-size: .36rem
			font-weight: bold
			text-align: center			
	.header-input
		flex: 1
		background: #fff
		height: .6rem
		line-height: .6rem
		border-radius: .1rem
		color:#ccc
		margin: .12rem 0rem 0rem .2rem
		padding-left: .2rem
	.header-right
		width: 1.24rem
		float: right
		text-align: center
		color: #fff
		.icon-arrow
			font-size: .15rem
			margin-left: -.05rem
</style>













