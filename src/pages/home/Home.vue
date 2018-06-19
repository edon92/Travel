<template>
	<div>
		<home-header :city="this.city"></home-header>
		<home-swiper :swiperList="this.swiperList"></home-swiper>
		<home-icon :iconList="this.iconList"></home-icon>
		<home-recommend :recommendList="this.recommendList"></home-recommend>
		<home-weeken :weekendList="this.weekendList"></home-weeken>
	</div>
</template>
<script>
	import HomeHeader from './components/Header'
	import HomeSwiper from './components/Swiper'
	import HomeIcon from './components/Icon'
	import HomeRecommend from './components/recommend'
	import HomeWeeken from './components/HomeWeek'
	import axios from 'axios'
	export default {
	  name: 'Home',
	  components: {
	  		HomeHeader,
	  		HomeSwiper,
	  		HomeIcon,
	  		HomeRecommend,
	  		HomeWeeken

	  },
	  data (){
	  	return {
	  		city: '',
	  		swiperList: [],
	  		recommendList: [],
	  		iconList: [],
	  		weekendList: []
	  	}
	  },
	  methods: {
	  	getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
   	 	},
	  	getHomeInfoSucc (res){
	  		res = res.data
	  		if(res.ret && res.data){
	  			const data = res.data
	  			this.city = data.city
	  			this.swiperList = data.swiperList,
	  			this.recommendList = data.recommendList
	  			this.iconList = data.iconList
	  			this.weekendList = data.weekendList
	  		}
	  	}
	  },
	  mounted (){
	  	this.getHomeInfo()
	  }
	}
</script>
<style type="text/css"></style>