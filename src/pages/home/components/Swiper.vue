<template>
	<div class="wrapper">
		<swiper :options="swiperOption" ref="mySwiper" v-if="showSwiper">
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
    props:{
      swiperList: Array
    },
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
	  		}
	  	}
	  },
    computed: {
      showSwiper (){
        return this.swiperList.length
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
    padding-bottom: 30.7%
    background: #eee
  		.swiper-img
  			width: 100% 
</style>