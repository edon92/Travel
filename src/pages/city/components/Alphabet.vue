<template>
  <div>
    <div class="list">
      <div class="list-item">A</div>
      <div class="list-item">A</div>
      <div class="list-item">A</div>
      <div class="list-item">A</div>
      <div class="list-item">A</div>
    </div>  
  </div>
</template>

<script>

export default {
  name: 'CityAlphabet',
}
</script>

<style lang="stylus" scoped>
@import '~styles/varible.styl'
  .list
    display: flex
    flex-direction: column
    justify-content: center
    position: absolute
    top: 1.5rem
    right: 0
    bottom: 0
    width: .4rem
    .list-item
      line-height: .6rem
      text-align: center
      color: $bgcolor
</style>
