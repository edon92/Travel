<template>
  <div>
    <div class="warrper-recommend">
      <div class="title">
        <span class="iconfont iconfont-fire">&#xe629;</span>
        热门推荐
      </div>
      <ul class="item-list">
        <li class="item border-bottom" v-for='item of recommendList' :key='item.id'>
          <img class="item-img" :src='item.imgUrl'>
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            <button class="item-button">查看详情</button>
          </div>
        </li>
      </ul>
    </div>
  </div>
  
</template>
<script >
  export default {
    name: 'HomeRecommend',
    props:{
      recommendList: Array
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
        color: #fd854c
    .item
      display: flex
      height: 1.9rem
      .item-img
        width: 1.7rem
        height: 1.7rem
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
          line-height: .7rem
          font-size: .32rem
          color: #ccc
          ellipsis()
        .item-button
          padding: .04rem
          background: #ff9300
          border-radius: .1rem
          color: #fff
    
  
</style>