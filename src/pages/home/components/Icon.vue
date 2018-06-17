<template>
	<div class="wrapper">
		<swiper :options="swiperOption">
			<swiper-slide v-for="(page,index) in pages" :key='index'>
				<div class="icons">
					<div class="icon" v-for="item of page" :key="item.id">
							<div class="icon-img">
								<img class="icon-img-content" :src='item.iconUrl'>
							</div>
							<P class="icon-desc">{{item.desc}}</P>
					</div>
				</div>
			</swiper-slide>
	  	<div class="swiper-pagination"  slot="pagination"></div>
		</swiper>
	</div>
</template>
<script>
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'
	export default {
	  name: 'HomeIcon',
	  components: {
	    swiper,
	    swiperSlide
	  },
	  data (){
	  	return{
	  		swiperOption: {
	  			pagination: '.swiper-pagination'

	  		},
	  		swiperList: [
	  			{
	  				id: '0001',
	  				iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
	  				desc: '景点门票'
	  			},
	  			{
	  				id: '0002',
	  				iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/27/dac2bcf9added702.png',
	  				desc: '丹霞山'
	  			},
	  			{
	  				id: '0003',
	  				iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png',
	  				desc: '玻璃栈道'
	  			},
	  			{
	  				id: '0004',
	  				iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
	  				desc: '夏日玩水'
	  			},
	  			{
	  				id: '0005',
	  				iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
	  				desc: '自然风光'
	  			},
	  			{
	  				id: '0006',
	  				iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/27/dac2bcf9added702.png',
	  				desc: '水上乐园'
	  			},
	  			{
	  				id: '0007',
	  				iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png',
	  				desc: '亲子游'
	  			},
	  			{
	  				id: '0008',
	  				iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
	  				desc: '名胜古迹'
	  			},
	  			{
	  				id: '0009',
	  				iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/27/dac2bcf9added702.png',
	  				desc: '景点门票'
	  			}
	  		]
	  	}
	  },
	  computed: {
			pages (){
				const pages = []
				this.swiperList.forEach((item,index) => {
					const page = Math.floor(index/8)
					if(!pages[page]){
						pages[page]=[]
					}
					pages[page].push(item)
				})
				return pages
			}			
	  }
	}
</script>
<style lang='stylus' scoped>
@import '~styles/varible.styl'
@import '~styles/mixins.styl'
  .wrapper >>> .swiper-pagination-bullets
    margin-bottom: -.2rem
    @media screen and (min-width: 660px)
      margin-bottom: 2.8rem
    .swiper-pagination-bullet
      background: $bgcolor
     	width: 6px 
      height: 6px 
      @media screen and (min-width: 660px)
        width: 8px 
        height: 8px 
  .icons
    margin-top: .1rem
    height: 0
    padding-bottom: 52%
    @media screen and (min-width: 660px)
    	margin-top: 1rem
    .icon
      position: relative
      overflow: hidden
      float: left
      width: 25%
      height: 0
      padding-bottom: 25%
      @media screen and (min-width: 660px)
      	margin-top: -1.4rem
      .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: .1rem
        @media screen and (min-width: 660px)
        	padding: 1rem
        	bottom: .2rem
        .icon-img-content
          display: block
          margin: 0 auto
          height: 100%
      .icon-desc
        position: absolute
        left: 0	
        right: 0
        bottom: 0
        height: .44rem
        line-height: .44rem !important
        text-align: center
        color: #212121
        ellipsis()
        @media screen and (min-width: 660px)
          font-size: .45rem
          height: .8rem
          line-height: .8rem !important
          bottom: .5rem
        @media screen and (min-width: 1000px)
          height: .8rem
          line-height: .8rem
          font-size: .55rem
</style>