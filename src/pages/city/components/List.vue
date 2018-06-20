<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="city-area">
        <div class="area-title">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
    </div>
      <div class="city-area">
       <div class="area-title">热门城市</div>
       <div class="button-list">
          <div class="button-wrapper">
            <div class="button" v-for="item in hotCities">{{item.name}}</div>
          </div>
        </div>
    </div>
        <div class="city-area" :ref=key v-for="(val,key) of cities">
          <div class="area-title">{{key}}</div>
          <div class="item-list" v-for="item in val">
            <div class="item border-bottom">{{item.name}}</div>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  methods: {
  },
  watch: {
    letter (){
      if(this.letter){
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted (){
    this.scroll = new BScroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varible.styl'
  .border-bottom
    &:before
      border-color: #ccc
  .list
    overflow: hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    .city-area
      text-indent: .1rem
      .area-title
        line-height: .54rem
        background: #eee
        padding-left: .2rem
        color: #666
        font-size: .26rem
      .item-list
        .item
          height: .64rem
          line-height: .64rem
      .button-list
        overflow: hidden
        padding: .1rem .6rem .1rem .1rem
        .button-wrapper
          display: flex
          flex-wrap: wrap
          .button
            width: 29%
            float: left
            // flex: 0 0 29%
            margin: .1rem
            padding: .1rem 0
            text-align: center
            border: .02rem solid #ccc
            border-radius: .06rem
            @media screen and (min-width: 760px)
              width: 31%
</style>
