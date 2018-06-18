<template>
	<div>
		<home-header></home-header>
		<home-swiper></home-swiper>
		<home-icon></home-icon>
		<home-recommend></home-recommend>
		<home-weeken></home-weeken>
	</div>
</template>
<script>
	import HomeHeader from './components/Header'
	import HomeSwiper from './components/Swiper'
	import HomeIcon from './components/Icon'
	import HomeRecommend from './components/recommend'
	import HomeWeeken from './components/HomeWeek'
	export default {
	  name: 'Home',
	  components: {
	  		HomeHeader,
	  		HomeSwiper,
	  		HomeIcon,
	  		HomeRecommend,
	  		HomeWeeken

	  }
	}
</script>
<style type="text/css"></style>