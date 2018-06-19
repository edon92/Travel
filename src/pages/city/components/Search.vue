<template>
  <div>
    <div class="search">
      <input placeholder="请输入城市" class="search-input">
    </div>
  </div>
</template>

<script>
export default {
  name: 'CitySearch',
}
</script>

<style lang="stylus" scoped>
@import '~styles/varible.styl'
  .search
    margin-top: -0.1rem
    background: $bgcolor
    padding: .1rem    
    .search-input
      box-sizing: border-box
      width: 100%
      padding: 0rem .1rem
      height:.62rem
      line-height: .62rem
      border-radius: .06rem
      color: #787878
      text-align: center

</style>
