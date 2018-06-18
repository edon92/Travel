<template>
  <div>
    <div class="warrper-recommend">
      <div class="title">
        <span class="iconfont iconfont-fire">&#xe629;</span>
        热门推荐
      </div>
      <ul class="item-list">
        <li class="item border-bottom" v-for='item of itemList' :key='item.id'>
          <img class="item-img" :src='item.src'>
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
    data (){
      return{
        itemList: [
          {
            id: '001',
            src: 'http://img1.qunarzz.com/sight/p0/1510/1b/1bc1aa482efaac090.img.jpg_200x200_286a571b.jpg',
            title: '广东韶关大唐花海',
            desc: '大唐花海位于韶关市曲江区，距韶关市中心和韶关高铁站仅半小时车程。项目总占地近万亩，现已对外开放的一期项目占地约2000亩，分为多个主题区域，并会根据季节变化更换花种，四季花影绰绰，时时花香萦绕。从高处鸟瞰，花海每个区域的造型也是一道亮丽的风景线，如风车，如彩虹，如蜻蜓，如巨大的七色花……是童话般浪漫的花之国度，是色彩奔放的梦幻之旅。'
          },{
            id: '002',
            src: 'http://img1.qunarzz.com/sight/p0/1605/7b/7b270a0b1dad062790.img.jpg_200x200_b235f5e2.jpg',
            title: '乳源广东大峡谷',
            desc: '大峡谷景区一带为平均海拔620米的山间盆地，夏季气候清凉怡人，平均常温22℃，房间不需要空调，是华南地区少有的避暑胜地。据地质学家考证，大峡谷属石英砂岩地貌，形成于距今一亿三千万年前的喜马拉雅造山运动。由于地壳曾几度升沉，地层断裂并经流水冲刷、风化侵蚀等作用，使大峡谷一带呈现出丰富的岩石层理，构成了现在大峡谷雄、奇、险、秀独特的自然景观。'
          },{
            id: '003',
            src: 'http://img1.qunarzz.com/sight/p0/1712/b5/b572e08138f4f6e6a3.img.jpg_200x200_bdff70e3.jpg',
            title: '天景山仙人桥',
            desc: '天景山仙人桥地处乳源瑶族自治县洛阳镇境内，距县城38公里，是往大峡谷景区的必经之地。景区内自然生态原始，景色迷人——集山水岩溶地貌、仙踪奇迹、道教文化、仙人桥于一体。主景区仙人桥高约138米，内拱106米，宽53米，长156米，秀、奇、峻、美的大自然令世人称绝。登临桥顶颇有“遗世而独立，羽化而登仙”之虞，实乃天上美景，人间仙境。'
          },{
            id: '004',
            src: 'http://img1.qunarzz.com/sight/p0/1603/4b/4b9c5fda7b0efd5190.img.jpg_200x200_22aedf25.jpg',
            title: '梅关古道',
            desc: '梅关位于距南雄市约30公里梅岭顶部。梅岭为五岭（大庚岭、骑田岭、萌渚岭、都庞岭、越城岭）之一大庚岭东段，大庚岭横亘广东、江西两省之间，全长200多公里。梅岭海拨只有400多米，但它处于大庚岭之咽喉，地势险要。在秦朝以前，五岭之南属南蛮之地，被古王朝列为疆域之外，那时的岭南车马不通，人烟稀少。'
          },
          {
            id: '005',
            src: 'http://img1.qunarzz.com/sight/p0/1510/1b/1bc1aa482efaac090.img.jpg_200x200_286a571b.jpg',
            title: '广东韶关大唐花海',
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