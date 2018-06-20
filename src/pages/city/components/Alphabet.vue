<template>
  <div>
    <div class="list">
      <div class="list-item" v-for="(val,key) of cities">{{key}}</div>
    </div>  
  </div>
</template>

<script>

export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  }
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
      line-height: .44rem
      text-align: center
      color: $bgcolor
</style>
