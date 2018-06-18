<template>
  <div>
    <div class="warrper-recommend">
      <div class="title">
        <span class="iconfont iconfont-fire">&#xe635;</span>
        周末去哪
      </div>
      <ul class="item-list">
        <li class="item border-bottom" v-for='item of itemList' :key='item.id'>
          <img class="item-img" :src='item.src'>
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
    data (){
      return{
        itemList: [
          {
            id: '001',
            src: 'http://img1.qunarzz.com/sight/source/1511/f7/90c1c5f6f3dd59.jpg_r_640x214_3cb4974e.jpg',
            title: '广东韶关大唐花海',
            desc: '大唐花海位于韶关市曲江区，距韶关市中心和韶关高铁站仅半小时车程。项目总占地近万亩，现已对外开放的一期项目占地约2000亩，分为多个主题区域，并会根据季节变化更换花种，四季花影绰绰，时时花香萦绕。从高处鸟瞰，花海每个区域的造型也是一道亮丽的风景线，如风车，如彩虹，如蜻蜓，如巨大的七色花……是童话般浪漫的花之国度，是色彩奔放的梦幻之旅。'
          },
          {
            id: '002',
            src: 'http://img1.qunarzz.com/sight/source/1506/45/313877f3917dbe.jpg_r_640x214_1c113e46.jpg',
            title: '佛山禅城大唐花海',
            desc: '大唐花海位于韶关市曲江区，距韶关市中心和韶关高铁站仅半小时车程。项目总占地近万亩，现已对外开放的一期项目占地约2000亩，分为多个主题区域，并会根据季节变化更换花种，四季花影绰绰，时时花香萦绕。从高处鸟瞰，花海每个区域的造型也是一道亮丽的风景线，如风车，如彩虹，如蜻蜓，如巨大的七色花……是童话般浪漫的花之国度，是色彩奔放的梦幻之旅。'
          },
          {
            id: '003',
            src: 'http://img1.qunarzz.com/sight/source/1508/f8/cadd4e229d3402.jpg_r_640x214_c38fb221.jpg',
            title: '江门海边大唐花海',
            desc: '大唐花海位于韶关市曲江区，距韶关市中心和韶关高铁站仅半小时车程。项目总占地近万亩，现已对外开放的一期项目占地约2000亩，分为多个主题区域，并会根据季节变化更换花种，四季花影绰绰，时时花香萦绕。从高处鸟瞰，花海每个区域的造型也是一道亮丽的风景线，如风车，如彩虹，如蜻蜓，如巨大的七色花……是童话般浪漫的花之国度，是色彩奔放的梦幻之旅。'
          },
          {
            id: '004',
            src: 'http://img1.qunarzz.com/sight/source/1505/4a/ac007012d54bd4.jpg_r_640x214_eefa6ade.jpg',
            title: '北京大唐花海',
            desc: '大唐花海位于韶关市曲江区，距韶关市中心和韶关高铁站仅半小时车程。项目总占地近万亩，现已对外开放的一期项目占地约2000亩，分为多个主题区域，并会根据季节变化更换花种，四季花影绰绰，时时花香萦绕。从高处鸟瞰，花海每个区域的造型也是一道亮丽的风景线，如风车，如彩虹，如蜻蜓，如巨大的七色花……是童话般浪漫的花之国度，是色彩奔放的梦幻之旅。'
          }
        ]
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