<template>
  <div>
    <div class="search">
      <input v-model="keyword" placeholder="请输入城市" class="search-input">
    </div>
    <div class="search-content" ref="wrapper" v-show="keyword">
        <ul>
          <li v-for="item of list" class="border-bottom search-item" @click="handleChangeCity(item.name)">
            {{item.name}}
          </li>
          <li v-show="hasNoData" class="border-bottom search-item">没有找到匹配的城市</li>
        </ul>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
import {mapState,mapMutations} from 'vuex'
export default {
  name: 'CitySearch',
  props:{
    cities: Object
  },
  data (){
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  methods: {
    handleChangeCity (city){
      this.changCity(city)
      this.$router.push('/')
    },
      ...mapMutations(['changCity'])
  },
  computed: {
    hasNoData (){
      return !this.list.length
    },
    ...mapState(['city'])
  },
  watch: {
    keyword (){
      if(this.timer){
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(()=>{
        const result = []
        for(let i in this.cities) {
          this.cities[i].forEach((value)=>{
            if (value.spell.indexOf(this.keyword) > -1 ||
              value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      },100)
    }
  },
  mounted (){
    this.scroll = new BScroll(this.$refs.wrapper)
  }
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
  .search-content
    z-index: 1
    overflow: hidden
    position: absolute
    top: 1.57rem
    bottom: 0
    left: 0
    right: 0 
    background: #eee
    .search-item
      line-height:.56rem
      height: .56rem
      font-size: .3rem
      padding-left: .2rem
      color: #666
      background: #fff
</style>
