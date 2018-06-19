<template>
  <div>
    <div class="header">
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
  name: 'City'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varible.styl'
  .header
    position: relative
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
