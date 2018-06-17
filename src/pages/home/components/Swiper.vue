<template>
	<div class="wrapper">
		<swiper :options="swiperOption" ref="mySwiper" >
	    <!-- slides -->
	    <swiper-slide v-for="item of swiperList" :key="item.id">
	    	<img class="swiper-img" :src="item.imgUrl">
	    </swiper-slide>
	    <!-- Optional controls -->
	    <div class="swiper-pagination"  slot="pagination"></div>
	  </swiper>
	</div>
</template>
<script>
	import 'swiper/dist/css/swiper.css'
	import { swiper, swiperSlide } from 'vue-awesome-swiper'
	export default {
	  name: 'Vue-Swiper',
	  components: {
	    swiper,
	    swiperSlide
	  },
	  data (){
	  	return {
	  		swiperOption: {
	  			pagination:'.swiper-pagination',
	  			loop: true,
	  			autoplay: 2000
	  		},
	  		swiperList: [
	  			{
	  				id: '0001',
	  				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/fc/e47aa3e1c67bbc02.jpg_750x200_0f3eecf8.jpg'
	  			},
	  			{
	  				id: '0002',
	  				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/11/947d8b7e221cbb02.jpg_750x200_4145c399.jpg'
	  			}
	  		]
	  	}
	  }
	}
</script>
<style lang='stylus' scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 26.7%
    background: #eee
  		.swiper-img
  			width: 100% 
</style>