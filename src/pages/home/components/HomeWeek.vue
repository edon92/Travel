<template>
  <div>
    <div class="warrper-recommend">
      <div class="title">
        <span class="iconfont iconfont-fire">&#xe635;</span>
        周末去哪儿
      </div>
      <ul class="item-list">
        <li class="item border-bottom" v-for='item of weekendList' :key='item.id'>
          <img class="item-img" :src='item.imgUrl'>
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
          </div>
        </li>
      </ul>
    </div>
  </div>
  
</template>
<script >
  export default {
    name: 'HomeWeeken',
    props: {
      weekendList: Array
    },
    data (){
      return{
      }
    }
  }
  
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl'
    .title
      margin-top: .2rem
      background: #eee
      height: .6rem
      line-height: .6rem
      font-size: .30rem
      .iconfont-fire
        color: #fc6356
    .item
      // height: 1.9rem
      .item-img
        // width: 1.7rem
        // height: 1.7rem
        width: 100%
        padding: .1rem
      .item-info
        min-width: 0
        margin-left: .1rem
        .item-title
          margin-top:.2rem
          font-size: .40rem
          ellipsis()
        .item-desc
          height: .7rem
          line-height:.7rem
          color: #ccc
          ellipsis()
</style>