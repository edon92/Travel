<template>
  <div>
    <div class="header-abs" v-show="showAbs">
      <router-link to="/">
        <span class="iconfont icon-back">&#xe624;</span>
      </router-link>
    </div>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <router-link to="/">
        <div class="header-left">
          <span class="iconfont icon-back">&#xe624;</span>
        </div>
      </router-link>
      <div class="header-city">城市选择</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Detail',
  data () {
    return {
      showAbs: true,
      opacityStyle : {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      console.log(123)
      if(top > 60){
        this.opacityStyle.opacity = top/140
        this.showAbs = false
      } else {
        this.showAbs = true 
      }
    }
  },
  activated () {
    window.addEventListener('scroll',this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll',this.handleScroll)
  }

}
</script>

<style lang="stylus" scoped>
@import '~styles/varible.styl'
  .header-abs
    z-index: 2
    position: absolute
    text-align: center
    top: .1rem
    left: .1rem
    width: .7rem
    height: .7rem
    line-height: .7rem
    border-radius: .35rem
    background: rgba(0,0,0,.4)
    .icon-back
      color: #fff
      font-size: .3rem
      font-weight: bold
  .header-fixed
    z-index: 2
    position: fixed
    left: 0
    top: 0
    width: 100%
    height: $headerHeight
    line-height: $headerHeight
    background: $bgcolor
    color: #fff
    .header-left
      position: absolute
      left: 0
      top: 0
      width: .64rem 
      text-align:center
      .icon-back
        font-size: .36rem
        font-weight: bold
        text-align: center
        color: #fff
    .header-city
      text-align: center
</style>